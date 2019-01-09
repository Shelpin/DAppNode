.. index:: ! Troubleshooting

.. Trobleshooting:

###############
Troubleshooting
###############

I can´t connect to the VPN when first installing DappNode
=========================================================

If the device with which you are trying to connect to your DAppNode is in the same local network as the DAppNode, you should have a router that supports NAT Loopback or edit the VPN configuration and change the Server IP to the internal IP of your DAppNode that you will find in the admin UI Dashboard, and in the console when you connect to the server via SSH. 
You can easily know if your router has NAT loopback enabled without accessing the router admin UI by opening your terminal and type ping + the IP of your DAppNode (where your VPN connection profile points to).
If the ping works without getting stuck your router has NAT Loopback so if you can´t connect to the VPN the cause is not being in the same network. Check that UDP ports 500 and 4500 are opened. 

More information about these issues in the "VPN Connection issues" section.

I can´t connect with another device to my DAppNode
==================================================

Only one device can access your DAppNode for each VPN credentials created; each device connected should have its own VPN configuration adding the desired devices in the Devices tab of your admin UI.  You can add as many devices as you want! Be nice and provide all your friends and family an access to the decentralized web please!!


My ETH node never ends up syncing
=================================

If you are not on an 8gb Ram configuration/your HD has not a high writing speed (ideally SSD), it might happen that the server is not able to catch up with Ethereum Blocks, so it never gets synced. We are sorry but the server might not be able to cope up with the chain.

It is also possible that the initial sync gets stuck at a given snapshot of the first sync if this happens try removing ETHCHAIN volume and let the sync  start again. To do so you have to enter in System / Ethchain / Open and  hit remove volume, the existing synced snapshots will be erased and th esync will start again. If you have a proper internet connection, a SSD disk and at least 4 GBs RAM the initial sync should be fine.  


I can´t access the ADMIN UI
===========================

You have to be connected to the VPN to access  the ADMIN UI, in case you are connected and still not able to access just disconnect the VPN and connect it again. 

I can´t install packages or it takes a lot of time to install them
==================================================================

For installing packages the ETH node should be synchronised. In case the node is sync and your are experience this, enter in System and restart IPFS and VPN and connect again. 


Ports that need to be opened 
============================

Please find in this table the ports that need to be opened for the smooth functioning of your DAppnode and installed packages.

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


However, if your router supports UPnP, do not worry about this, it will manage all the ports stuff for you. 
