:original_name: vpn_01_0035.html

.. _vpn_01_0035:

IPsec VPN
=========

Internet Protocol Security (IPsec) VPN uses a secure network protocol suite that authenticates and encrypts the packets of data to provide secure encrypted communication between different networks.

In the example shown in :ref:`Figure 1 <en-us_topic_0000001937647862__en-us_topic_0000001592693925_fig1673177194510>`, assume that you have created a VPC with two subnets (192.168.1.0/24 and 192.168.2.0/24) on the cloud, and the router in your on-premises data center also has two subnets (192.168.3.0/24 and 192.168.4.0/24). In this case, you can create a VPN to connect the VPC subnets and the data center subnets.

.. _en-us_topic_0000001937647862__en-us_topic_0000001592693925_fig1673177194510:

.. figure:: /_static/images/en-us_image_0000001960951864.png
   :alt: **Figure 1** IPsec VPN

   **Figure 1** IPsec VPN

Site-to-site VPN is supported to enable communication between VPC subnets and on-premises data center subnets.
