:original_name: vpn_faq_00031.html

.. _vpn_faq_00031:

What Are the Typical Scenarios of IPsec VPN?
============================================

A VPN is a point-to-point connection that implements private network access between two points.

-  Applicable scenarios:

   -  A VPN is created between different regions to enable cross-region VPC communications.
   -  A VPN hub is used together with VPC peering connections and Cloud Connect connections to enable communications between an on-premises data center and multiple VPCs on the cloud.
   -  A VPN is used together with source NAT to enable access to specific IP addresses across clouds.

-  Not applicable scenarios:

   -  A VPN cannot be used to connect VPCs in the same region. It is recommended that you use VPC peering connections to enable communications between VPCs in the same region.
   -  A VPN cannot be used between the cloud and your home network that uses PPPoE dial-up.
   -  A VPN cannot be used between the cloud and 4G/5G routers.
   -  A VPN cannot be used between the cloud and your personal terminals.
