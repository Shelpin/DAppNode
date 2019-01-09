.. index:: ! FAQS

.. FAQS:

############################
FAQ´s
############################

What are the hardware minimum requirements for DAppNode to work ?? 
==================================================================

It depends on the use you want to do with it, basically the number  of nodes / DApps that you want to host in it. A basic setup is at least 4 gbs RAM (ideally 8GBs) and a 200 GBs SSD disk, it is important that the disk is SSD, otherwise writing speed won´t be able to cope with the ETH chain sync. On top  of that requirements add capacity as needed to run the nodes  you wish to run.  

Can I run DAppNode in a laptop??
================================

Yes you can!!! Different thing is if you will be able to get any relevant proof of work reward, what does not seem very likely talking about the main cryptocurrencies. Still DAppNode is a great solutions for hosting your proof of stake nodes and get some coins out of your stake easily and securely stored in your DAppNode, or mine new cryptocurrencies that are CPU mineable and still low difficulty.     

Can I run DAppNode  in a cloud service?
=======================================

Technically you can, and we  recognise is the best  way to try it and check how wonderful it is before buying a dedicated piece of hardware. However that defeats the whole purpose of DAppNode mission about building a self owned and censorship resistant infrastructure layer… so please if you want to try it in a VPS please do, but then move it to your own piece of  hardware (it will also be cheaper )

Why should I run a DAppNode?
============================

Centralization of blockchain networks and infrastructure is a huge problem for the whole bloockchain vision, that can even make it dystopian. By running your own nodes you contribute to decentralization and censorship resistance of blockchain networks with a higher degree of privacy while getting some incentives for sharing your infrastructure if you wish to!

Can i share my DAppNode?
========================

You can and you should!!! The devices tab of the DAppNode it is thought for you to add your beloved ones to access/use your DAppNode. You just generate his/her credentials from the ADMIN UI and they can connect via VPN to your DAppNode and use a trusted infrastructure as a gateway to the decentralized web.  

Can i use metamask  / my  crypto connected to my own DAppNode node?
===================================================================

Yep!!! You can customise the nodes your metamask or mycrypto connect to point to your very own node!!!To do so you just have to add the RPC URL http://my.ethchain.dnp.dappnode.eth:8545 

Can i install DAppNode in  a Raspberry Pi with extra storage?
=============================================================

Unfortunately not at the moment, DAppNode includes an Ethereum full node  and a IPFS node by default so they need a powerful hardware to be run on that a Raspberry pi with extra storage cannot provide. 

If  DAppNode is free how do you maintain operations/development??
==================================================================

DAppNode software is an open source platform developed by the non profit association DAAppNode association in Zug. DAppNode Association is driven and funded by the community, at the moment we have three grants from EF, Aragon and ECF, but the association also has sustainabiliity sources relying on projects that want their package uploaded  to DAppNode and featured in the installer section,authorised hardware resellers make a donation to the association for every piece of hardware with DAppNode pre installed they sell and we are also backed by individual donors and supporters.  

Can i upload my own packages to DAppNode?
=========================================

Yes!! We have developed an SDK to make the loading of packages to DAppNode easy for everyone. Check this doc! https://github.com/dappnode/DAppNodeSDK/wiki/DAppNode-SDK-tutorial

Do I need technical knowledge to install / run a DAppNode?
==================================================================

No! One of our the critical aspects to achieve our objectives,  is eliminating the technical friction to install and run nodes so a minimum knowledge is enough to run your own DAppNode. If you know how to open the terminal and run a couple of commands in the console terminal you are done!

Can I use IPFS once DAppNode is installed ??
============================================

Yes!Take in account that IPFS is a core component of DAppNode itself , used for example to host the packages to be downloaded but you can also use it your own, as you  have a totally functional IPFS node. You can access to it by typing http://my.ipfs.dnp.dappnode.eth:5001/webui 

The first time you access to it will ask you for your “Custom API address”, just fill the field with this address and you will be connected to your IPFS node. This is the input you have to enter in the field "Is your API in a port other than 5001?
/ip4/172.33.1.5/tcp/5001

Is there any way to have a Web GUI for the Parity client?
=========================================================

Since we updated from Parity 2.1.6 to newer versions ,  WEB GUI support has been deprecated by Parity, so at the moment the only way to interact with your node is through the command line. We are looking for solutions but it is not an easy issue. 



