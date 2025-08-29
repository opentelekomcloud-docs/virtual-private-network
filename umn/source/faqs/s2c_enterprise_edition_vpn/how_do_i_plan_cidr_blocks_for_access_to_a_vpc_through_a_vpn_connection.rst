:original_name: vpn_faq_00036.html

.. _vpn_faq_00036:

How Do I Plan CIDR Blocks for Access to a VPC Through a VPN Connection?
=======================================================================

-  The CIDR blocks of a VPC cannot conflict with on-premises CIDR blocks.

-  To avoid conflicts with cloud service addresses, do not use 127.0.0.0/8, 169.254.0.0/16, 224.0.0.0/3, 100.64.0.0/10, 100.64.0.0/12, and 214.0.0.0/8 for your on-premises network.

   If you need to use 100.64.0.0/10 or 100.64.0.0/12, submit a service ticket.
