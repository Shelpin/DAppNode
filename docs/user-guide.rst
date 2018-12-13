.. index:: ! userguide

.. userguide:

################################
Introduction - What is DAppNode?
################################

Welcome to DAppNode!!! 

If you are reading this, decentralization, privacy and security are important to you and we’re glad for that, and even more for helping people like you run their own secured hardware towards that which contributes to a truly decentralized web. 

DAppNode is an operating system that allows you to host decentralized apps in a truly decentralized way, eliminating the reliance on vulnerable third parties and adds an extra layer of incentivization that helps to spread adoption of the blockchain ecosystem, and most important, solves the problem of infrastructure centralization. 

You can install DAppNode on any piece of hardware (see minimum requirements)  to get easy censorship-resistant access to your favorite DApps, the ability to host your own nodes and share access with family and friends. 

Our goal is to achieve “real decentralization” by creating a layer of personally owned hardware infrastructure that is easy to set up and provides secure access. 

DAppNode connects users to the decentralized web and creates the infrastructure for DApps to run services 24x7 in a truly decentralized manner.

We also developed an SDK for DAppNodePackage developers and we expect to see many DApps with their own DNP that improve the user experience and decentralizes access. For example, it can be a DApp accelerator that allows the devices not having to synchronize the chain to start using it, like a cache system for the DAppNode users. It could be a prepared service for staking in any chain, it could be a client for other chains, or it could be a scrawl of a decentralized search engine, etc.
Within the DAppNode project we have a storefront that will allow any person to install and configure their own project in just minutes, facilitating the visibility and decentralization of its growth and expansion. We believe this is the beginning of a new model, a P2P economy that makes projects truly decentralized and accessible to anyone.
We envision a self-sustaining system where users support their favorite projects, by providing the service that the project needs and in return it provides the necessary income to amortize the costs of the DAppNode.

The Desired Final User Story
============================

1.	Vojtech has several cryptocurrencies he follows and is ready to stop using his laptop to run clients but doesn’t want to have to pay a monthly subscription in fiat to some company he doesn’t trust with his private keys.

2.	He hears about DAppNode and decides to buy the top of the line DAppNode Server preloaded from one of the many certified independent vendors (though he could buy his own server and install the software himself).

3.	The DAppNode Server is delivered to his front door, and when Vojtech opens the box he finds a 2 step instruction card: First, plug in the Server. Second, go to dappnode.org/initialize

4.	On this website, there is an extremely simple and short walk-thru for Vojtech to set up his credentials and choose which clients to deploy.

5.	By just checking a few boxes, Vojtech deployed his own VPN; his own local instance of MyCrypto.com; Ethereum, Bitcoin, Monero and Dogecoin Full nodes; a ZenCash Secure Node and DASH Master Node; he joined the IPFS Consortium and deployed a TrueBit Verifier and Livepeer node; and hosted Giveth, Swarm City, Aragon, Colony, and Decentraland Helper DApps to support these projects and to ensure that his interaction with these DApps cannot be censored and are fully trustless.

6.	Vojtech then tells his friends and family that he is the admin for his own DAppNode and he is able to give them a link that sets them up with their own credentials and access to his DAppNode, and Vojtech can deploy any other DApps that he or his friends and family want to have hosted with a couple clicks. He has become the trusted gateway to the decentralized world for his entire community.

7.	Vojtech ends up being able to pay off the cost of his DAppNode in 2 months with the profits made from his ZenCash, Swarm City, DASH and TrueBit Nodes. He also canceled his VPN and all of his Digital Ocean accounts because now he has his own server that he can host all of his services on. Without even trying, Vojtech has a couple extra hundred dollars a month because he is running DAppNode on his own personal server.

We started working on this project mostly part-time in October 2017; now we have a team of 6 working full time. We have a fully functional MVP version that we have been sharing with the community. We expect to partner with hardware manufacturers once we have a few more iterations of the software completed.

We have been developing in an invitingly open source manner and now that the software is completed anyone can use their own hardware to run DAppNode on it.

This project is a community funded and fully open sourced project that has received support from Ethereum Foundation, Ethereum Community Fund, Eth Prize, Aragon NEST, GitCoin and private donors. 

We are open to receive donations from any interested parties to help pay the developers working hard on the software development. 

See our campaign on Giveth.io to make a donation:  https://beta.giveth.io/campaigns/5b44b198647f33526e67c262

Ready to jump in??? Here we go!

##############################
How can you install DAppNode ?
##############################

Think of DAppNode as an operating system. In fact, it is; our savvy team has taken an Ubuntu distribution and superpowered it to be your gateway to access the decentralized web.

Minimum requirements
====================

You will need a dedicated machine to install it. 

Ethereum is big! To cope with that, you’ll need to have a powerful enough machine to keep up with Ethereum’s rapidly splitting blocks. 

That is why we recommend having at least 8gbs RAM and a SSD hard drive with at least 160 GBs (add capacity as you like, keep in mind that Ethereum is 130GBs at press time). 

How to install Dappnode on your machine
=======================================

Okay, so you’re ready to join the real DAppers. Let us show you how to make that hardware sing the hardware decentralization song!

How to install DAppNode from an ISO
-----------------------------------

Download the image from  `DAppNode-ubuntu-18.04-server-amd64_v0.1.3.iso <https://github.com/dappnode/DAppNode/releases/download/v0.1.3/DAppNode-ubuntu-18.04-server-amd64_v0.1.3.iso>`_  or `build it  from source <https://github.com/dappnode/DAppNode_Installer>`_

Burn the ISO in a USB (~8 min)
------------------------------
Burn the ISO to an USB stick, please follow the official Ubuntu instructions for `MacOS <https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-macos#0>`_, `Windows <https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-windows#0>`_  or `Ubuntu <https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-ubuntu#0>`_.

Please note that these instructions are intended to generate the ISO image in a bootable USB from a Mac, Windows or Linux device , and then install it in a server. ***IF YOU EXECUTE THE BOOTABLE USB IN A MACHINE CONTAINING DATA IT WILL BE ERASED.*** DAppnode is intended to run 24/7 so if you install it in a laptop or desktop machine and you turn it off it will lose the sync

Install an Ubuntu distribution (~15 min)
----------------------------------------

Insert the USB into your Server and prepare to install an Ubuntu distribution. You will have to make sure that your Server boots from the USB. If you succeed at booting up from your USB, you will be greeted with this screen or a similar one:

.. image:: https://github.com/Shelpin/DAppNode/blob/master/doc/dappnode-installation-welcome-screen.png
   :width: 300 px
   :align: center
   
Follow the Ubuntu installation steps; various screens will guide you through the process. You can follow this standard option for a default installation:

Recommended setup
-----------------

Note by following these instructions you will erase your Server's disk contents.

1.	***Select a language*** - Language: [English]
2.	***Select your location*** - Country, territory or area: [United States]
3.	***Configure the keyboard*** - Detect keyboard layout? [Yes] Follow the instructions to detect your keyboard
4.	***Configure the network*** - Hostname: [DAppNode]
5.	***Set up users and passwords*** - Full name for the new user: [DAppNode]
6.	***Set up users and passwords*** - Username for your account: [dappnode]
7.	***Set up users and passwords*** Choose a password for the new user: [YOUR_PASSWORD]
8.	***Set up users and passwords*** - Re-enter password to verify: [YOUR_PASSWORD]
9.	***Set up users and passwords*** - Encrypt your home directory? [No]
10.	***Configure the clock*** - Is this time zone correct? [Yes]
11.	***Partition disk*** - Partitioning method: [Guided - use entire disk and set up LVM]
12.	***Partition disk*** - Select disk to partition: [SCSI33 (0,0,0) (sda) - ...]
13.	***Partition disk*** - Write the changes to disks and configure LVM? [Yes]
14.	***Partition disk*** - Amount of volume group to use for guided partitioning: [Continue]
15.	***Partition disk*** - Write the changes to disks? [Yes]
16.	***Configure the package manager*** - HTTP proxy information (black for none): [Continue]
17.	***Configuring tasksel*** - How do you want to manage upgrades on this system? [Install security updates automatically]
18.	***Software selection*** - Choose software to install [OpenSSH server] Use the arrows to navigate to the option, and the spacebar to select it.
19.	***Install the GRUB boot loader on a hard disk*** - Install the GRUB boot loader to the master boot record? [Yes]
20.	***Finish the installation*** - Installation complete [continue]

If the installation succeeded, your system will reboot, you will have to log in with the user and password provided in the installation, and it should finish with this screen:

.. image:: https://github.com/Shelpin/DAppNode/blob/master/doc/dappnode-installation-ending-screen.png?raw=true
   :width: 300 px
   :align: center
   
Installation via script
=======================

WARNING
-------
This software is not meant to be run in a remote machine hosted by any remote provider. What DAppNode specifically wants to avoid is  centralization of the machines that our digital lives rely on; nevertheless we understand that before buying a dedicated machine to run your Dappnode you might want to test it and see how easy it is to use….

And… only for that reason will we look aside when someone installs a DAppNode in a virtual provider. We want it to be clear that kind of use is not the recommended use, but for testing purposes only. 

Remember: ***Your hardware, your coins, your privacy, your freedom.***

Script installation guide
_________________________

For this example we'll be installing DAppNode on a Digital Ocean droplet, but the process should work for any other Ubuntu Server 18.04. 

***We strongly recommend using 8GB+ of RAM and a 160Gb+ SSD hard drive.***

Install DAppNode and its dependencies
_____________________________________

Install the prerequisites (docker and docker-compose) running this command in the terminal of the machine you want to install  the DAppNode server,if using a Virtual Service Provider, you have first to connect you via SSH to that machine.

``sudo wget -O - https://github.com/dappnode/DAppNode/releases/download/v0.1.3/dappnode_install_pre.sh | sudo bash``

Install DAppNode
________________

``sudo wget -O - https://github.com/dappnode/DAppNode/releases/download/v0.1.3/dappnode_install.sh | sudo bash``

If you have an static IP and want to set it up right from the connection, then run the command with the following variable including your staatic ip

``sudo wget -O - https://github.com/dappnode/DAppNode/releases/download/v0.1.3/dappnode_install.sh | sudo STATIC_IP="your static IP" bash``

When the installation is done and is successful, you will be given credentials to connect to your DAppNode. 

Take into account that the chain will take some time to synchronize and you will not be able to perform most of the actions before that.


##################
Connect to the VPN
##################

Once you have your DAppnode running, you will get an URL in your terminal from where you can download the VPN config file and install it on your device. Just download it and follow the instructions. For Android, Ubuntu and Windows you have to set the VPN following the instructions.

Installing (or manually setting up)this VPN file will configure your VPN connection to your DAppNode from your device. The first device VPN connection will have super admin privileges so you can access and manage the DAppnode admin UI; this user cannot be deleted.

Take into account that some VPN clients might send all traffic through the VPN, which is not very ideal if you have many  people connected to your DAppNode, or only to send traffic which points to an ETH domain. 

DAppNode is not intended to manage all the traffic of the devices connected to it, only the ETH domains access requests.
As a general rule, if your DAppNode is not connected through a router that supports UPnP, you will have to manually open some ports to have complete functionality. For the VPN to work you must make sure that you have opened the 4500 and 500 ports (UDP). 

Here you have a sample table of the ports that should be opened in your DAppNode: 

.. list-table::
   :widths: 25 25 50
   :header-rows: 1
   

   * - **Service** 
     - **TCP**
     - **UDP**
   * - VPN
     -
     - 500,4500
   * - SSH
     - 22
     - 
   * - Ethereum Node
     - 30303
     - 30303
   * - IPFS
     - 4001
     - 4002
     
     
If you are not able to download or install the config file, you can set it up manually following the instructions for different platforms contained in the link that the terminal gives after installation. All the parameters you need to fill in are given by your terminal when you first install it or when you connect to it vía SSH. 

These are the parameters you will need to configure, still  depending on your operating system follow the instructions you will find in the website  you will be directed to. 

.. image:: https://github.com/Shelpin/DAppNode/blob/master/doc/credentialsscreen.png
   :width: 300 px
   :align: center
   
   
**VPN TYPE**: Select L2TP over IPSEC
**Server IP**: Select the IP given by the terminal when connecting to the DAppNode via SSH. If you are behind a router without NAT Loopback,  you will also find in the terminal the internal IP you need to use to be able to connect being in the same network without NAT Loopback enabled.
**PSK**: Shared secret, you will find it in the terminal. 
**VPN User**: This is the username of the super administrator and your terminal will give it to you too.
**Password**: You can also find the password in the terminal output when connecting to your DAppNode. 

Now it is time…

####################
Enter  your DAppNode
####################

Navigate to my.admin.dnp.dappnode.eth to access DAppNode's administrative page. Bear in mind that DAppNode's functionality will be limited until the Ethereum mainnet chain is synced (should take around 2~3 hours to get a snapshot).

Now you can do things like for example:

●	Navigate to a decentralized web `decentral.eth <http://decentral.eth>`_:

●	Decentralized version of `Mycrypto <http://mycrypto.dappnode.eth>`_

●	Decentralized version of `ENS Manager <http://ens.dappnode.eth>`_

●	Decentralized version of `Wallet Gnosis <http://gmultisig.dappnode.eth>`_

●	Go to IPFS by entering http://my.ipfs.dnp.dappnode.eth:5001/webui into your browser.

●	You have a websocket of your parity node in ws://my.ethchain.dnp.dappnode.eth:8546 and you can  use http://my.ethchain.dnp.dappnode.eth:8545 as a custom RPC to connect to metamask i.e 



   
   

     























   















