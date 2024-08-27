:original_name: vpn_08_0323.html

.. _vpn_08_0323:

How Many VPN Connections Do I Need to Connect to Multiple On-premises Servers?
==============================================================================

VPN uses the IPsec technology to connect your on-premises data center to a VPC on the cloud. As such, the number of VPN connections is related to the number of data centers where the servers to be connected to the cloud are located, but not to the number of servers.

In most cases, one on-premises data center has one public gateway. All servers connect to the Internet through this gateway. Therefore, you only need to configure one VPN connection to allow communications between the VPC and your on-premises data center.
