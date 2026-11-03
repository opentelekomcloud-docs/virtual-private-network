:original_name: vpn_08_0305.html

.. _vpn_08_0305:

What Are the Differences Between the Application Scenarios and Connection Modes of IPsec and SSL VPNs?
======================================================================================================

Scenarios
---------

IPsec VPN connects two LANs, such as a branch and its headquarters (or a VPC), or an on-premises data center and a VPC.

SSL VPN connects a client to a LAN. For example, the portable computer of an employee on a business trip accesses the internal network of the company.

Connection Modes
----------------

IPsec VPN requires fixed gateways, such as firewalls or routers, at both ends. The administrator needs to configure gateways at both ends to complete IPsec VPN negotiation.

SSL VPN needs to install a specified client software on the server, then the server connects to the SSL device through the username and password.

|image1|

.. note::

   Currently, only IPsec VPN is supported; SSL VPN is not supported.

.. |image1| image:: /_static/images/en-us_image_0000001542174462.png
