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

Upload to IPFS
--------------

When uploading content to IPFS we use a tool we have created that can be used if you are connected to DAppNode (this tool is currently experimental, and will be improved in the coming months) or you could use the command ``ipfs add -r build``.

Using our tool the next steps would be:

``$cd ..``

``$npm install -g @dappnode/ipfsuploader``

``$ipfsuploader build/``

After executing the last command you will obtain a similar output (they will not be the same hashes) to this one:

``Qmb5oxJWf5Zw1UnvewkRM6V5qVbxWcY5s59FvhtWhC6F4Fbuild/i18n``

``QmQV1tXNCZsD82LiLwWpHvdwWqbGXJd8q1Pq2hMPxyiKFabuild/packages/es5-shim``

``QmTte2i1HQKRgUgA8ZuVANwmqLCjjYzddmCekbUqJ3fmCAbuild/packages/ethereum_dapp-styles/fonts``

``QmWMVompWymG8CmCgyB57dvaWegymjknMFTUQVrWfYebYubuild/packages/ethereum_dapp-styles/icons``

``QmTCXm13p6PW7CnKegNqFP3mCgt8sAaNNteCJDjFiGP3Jmbuild/packages/ethereum_dapp-styles``

``QmVvCPByChGfmEvxS2Nv6icKZSJ27aYqDSUzP2gta44XYbbuild/packages/ethereum_elements``

``QmXQ6fGzJsDAUGuLFxG8wgMgvyvgnR6pW9yeue3VUtdHnebuild/packages``

``QmTRpmNWiAkYQnesiGZRVE9NwbEfqZLH4DnLmbCmjMGaLLbuild/sockjs``

``QmZQ3GzqXHCRM6uccP6TcZdPGPSyqJXyhwLETD2T2o8m73build``


If we use the hash associated with `build` and access it through this URL:

http://my.ipfs.dnp.dappnode.eth:8080/ipfs/QmZQ3GzqXHCRM6uccP6TcZdPGPSyqJXyhwLETD2T2o8m73 

The website is now distributed in IPFS!

Point the ENS domain to the IPFS hash
--------------------------------------

If you are the owner of an ENS domain you can make this point to the hash you want. We are going to use `wallet.dappnode.eth <http://wallet.dappnode.eth>`_ for this example:

1.	Go to http://mycrypto.dappnode.eth/#contracts (if you don’t have access to a DAppNode you can use the centralized alternative) https://mycrypto.com#contracts or https://www.myetherwallet.com/#contracts)

2.	Select: ENS: Public Resolver 0x5FfC014343cd971B7eb70732021E26C35B744cc4

3.	Access

4.	Go to https://etherscan.io/enslookup and search for wallet.dappnode.eth noting its NameHash (in this case 0x7407….8c02)

5.	setText

   **node bytes 32:** 0x7407156505d4facdb6474ccee4aac0c34679f5d6fddb603ab6e8976d8e138c02
   
   **key:** dnslink
   
   **value:**/ipfs/QmZQ3GzqXHCRM6uccP6TcZdPGPSyqJXyhwLETD2T2o8m73
   
.. image:: https://github.com/Shelpin/DAppNode/blob/master/doc/enstransaction.jpg
   :width: 500 px
   :align: center
   
   
   
   

