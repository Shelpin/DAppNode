.. index:: ! Advanced users bonus

.. Advanced users bonus:

################################
Advanced users bonus
################################

Have your own packages in your DappNode
=======================================

You have two ways to install your own DNPs (DAppNode Packages):

1.	With their ENS name, i.e. kovan.dnp.dappnode.eth (a private repo controlled by our team) or yourpackage.public.dappnode.eth, a repo with free access is available so anyone can publish packages there. 

Ultimately any ENS name that resolves to an IPFS containing a valid manifest is acceptable.

2.	With an IPFS hash that contains a valid manifest, i.e. /ipfs/QmR28vMrQVkSLznCQF7G1eNPx3RBx27zKYpctwwgRAot9W

So for development what we recommend is:

 1. Develop your package and test it locally
 2. Use the SDK to build it and upload it to IPFS
 3. Test the package by installing it with its IPFS link
 4. Once you are sure it works perfect, publish it to the open repo public.dappnode.eth.

Please take a look at these refs regarding the SDK to deploy your own packages in your DAppnode: 

https://github.com/dappnode/DAppNodeSDK
 
https://github.com/dappnode/DAppNode/wiki/DAppNode-Package-Development
 
https://github.com/dappnode/DAppNode/wiki/DAppNode-packages-manifest


How to decentralize wallet.ethereum.org with DAppNode
=====================================================

In this section, we’re going to explain how it’s possible to decentralize wallet.ethereum.org using DAppNode and by decentralize we mean; distribute it’s content through IPFS, making it possible to resolve via an ENS address.

Our first step is to clone the wallet.ethereum.org repository and follow the steps of the official guide, here (this tutorial is based on this commit `6a6463b1a6aa615e4364592c12c933ee816fb28b) <https://github.com/ethereum/meteor-dapp-wallet/tree/6a6463b1a6aa615e4364592c12c933ee816fb28b>`_.


Here’s a summary of the steps that we will need to follow:

# Install Meteor:

``$ curl https://install.meteor.com/ | sh``

``$ git clone https://github.com/ethereum/meteor-dapp-wallet.git``

``$ cd meteor-dapp-wallet/app``

``$ npm install``

``$ npm install -g meteor-build-client``

``$ meteor-build-client ../build - path ""``

After following these steps we will have a folder called `build` with a deployable version of wallet.ethereum.org.

In order for us to use the web inside DAppNode a site must be a static website that can be used directly from IPFS (another case would be a website with an accelerator or a DAppNode Package API installed to act as a backend). If we must make these modifications, the modifications will depend on each website and how it has been developed.

``meteor-dapp-wallet/app/client/lib/ethereum/1_web3Init.js``

Change:

web3 = new Web3('ws://localhost:8546');

By:

web3 = new Web3('ws://my.ethchain.dnp.dappnode.eth:8546');

After this step, the wallet will connect directly to our DAppNode, in case of not being able to go through MetaMask. 

``meteor-dapp-wallet/app/client/lib/ethereum/observeTransactions.js``

In line 532 change:

Session.get('network') == 'main' &&

By:

Session.get('network') == 'centralized' && false &&

The reason we need to make this change is that we do not want the website to connect to centralized services like min-api.cryptocompare.com. Making this change means that we lose the functionality which converts the eth to other currencies, in future versions this service should be replaced by a decentralized service to get the exchange rate.

``meteor-dapp-wallet/app/client/lib/ethereum/walletConnector.js``

There seems to be a problem with the EthAccounts.init so we have to wrap line 86

try {
   EthAccounts.init();
} catch (err) {
   console.log(err);
}
Then comment `EthTools` on line 89, to avoid min-api.cryptocompare.com calls

/*
   EthTools.ticker.start({
   extraParams: typeof mist !== 'undefined' ? 'Mist-' + mist.version : '',currencies: ['BTC', 'USD', 'EUR', 'BRL', 'GBP']   });
*/

``meteor-dapp-wallet/app/client/routes.js``

To redirect on start to dashboard modify line 14:
if (location.origin === 'file://') {

To:

if (location.origin === 'file://' || location.origin === 'http://my.ipfs.dnp.dappnode.eth:8080') {

Solve SourceSansPro-ExtraLightIt error

``wget -O ../build/packages/ethereum_dapp-styles/fonts/SourceSansPro-ExtraLightIt.otf https://www.wfonts.com/download/data/2015/10/11/source-sans-pro-extralight/Source%20Sans%20Pro%20ExtraLight%20Italic.otf``

Once these steps are finished we’re in a position to create a new build:

``$ meteor-build-client ../build — path ""``



