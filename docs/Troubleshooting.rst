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

I can´t connect with another device to my DAppNode
==================================================

Only one device can access your DAppNode for each VPN credentials created; each device connected should have its own VPN configuration adding the desired devices in the Devices tab of your admin UI.  You can add as many devices as you want! Be nice and provide all your friends and family an access to the decentralized web please!!


My ETH node never ends up syncing
=================================

If you are not on an 8gb Ram configuration/your HD has not a high writing speed (ideally SSD), it might happen that the server is not able to catch up with Ethereum Blocks, so it never gets synced. We are sorry but the server might not be able to cope up with the chain.  


Ports that need to be opened 
============================

Please find in this table the ports that need to be opened for the smooth functioning of your DAppnode and installed packages.


However, if your router supports UPnP, do not worry about this, it will manage all the ports stuff for you. 
