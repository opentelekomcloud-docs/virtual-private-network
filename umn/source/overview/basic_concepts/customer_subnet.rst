:original_name: vpn_01_0017.html

.. _vpn_01_0017:

Customer Subnet
===============

Customer subnets are subnets in an on-premises data center that access a VPC on the cloud through a VPN. You need to enter subnets using CIDR notation (example: 192.168.0.0/16), and with each entry separated by a comma.

After configuring a customer subnet, you do not need to add a route for it. The VPN service will automatically deliver routes pointing to the customer subnet.

.. note::

   A customer subnet cannot be set to a Class D or Class E IP address or an IP address starting with 127.
