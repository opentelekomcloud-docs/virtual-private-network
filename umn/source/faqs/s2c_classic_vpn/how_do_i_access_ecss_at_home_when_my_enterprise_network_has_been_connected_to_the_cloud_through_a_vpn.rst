:original_name: vpn_08_0318.html

.. _vpn_08_0318:

How Do I Access ECSs at Home When My Enterprise Network Has Been Connected to the Cloud Through a VPN?
======================================================================================================

A VPN is an IPsec VPN that connects a VPC on the cloud and an on-premises local area network (LAN).

The home network is not a part of the LAN of your enterprise and cannot be directly connected to the VPC on the cloud.

If your host at home needs to access VPC resources on the cloud, your host can directly access the EIP of the cloud service or connect to the LAN of your enterprise through SSL VPN (if your enterprise supports SSL access) and then access VPC resources on the cloud through the LAN.
