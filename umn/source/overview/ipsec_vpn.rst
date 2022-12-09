:original_name: en-us_topic_0160974607.html

.. _en-us_topic_0160974607:

IPsec VPN
=========

The Internet Protocol Security (IPsec) VPN is an encrypted tunneling technology that uses encrypted security services to establish confidential and secure communication tunnels between different networks.

In :ref:`Figure 1 <en-us_topic_0160974607__fig489417475262>`, a VPC has two subnets: 192.168.1.0/24 and 192.168.2.0/24. On your router deployed in your physical data center, you also have two subnets: 192.168.3.0/24 and 192.168.4.0/24. You can use VPN to enable subnets in your VPC to communicate with those in your data center.

.. _en-us_topic_0160974607__fig489417475262:

.. figure:: /_static/images/en-us_image_0170041086.png
   :alt: **Figure 1** IPsec VPN

   **Figure 1** IPsec VPN

Currently, the site-to-site VPN and hub-spoke VPN are supported. You need to set up VPNs in both your data center and the VPC to establish the VPN connection.

You must ensure that the VPN in your VPC and that in your data center use the same IKE and IPsec policy configurations. Before creating a VPN, familiarize yourself with the protocols described in :ref:`Table 1 <en-us_topic_0160974607__en-us_topic_0030969429_en-us_topic_0030119097_table19214078112957>` and ensure that your device meets the requirements and configuration constraints of the involved protocols.

.. _en-us_topic_0160974607__en-us_topic_0030969429_en-us_topic_0030119097_table19214078112957:

.. table:: **Table 1** Involved protocols

   +-----------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
   | Protocol              | Description                                                                                                        | Constraint                                                      |
   +=======================+====================================================================================================================+=================================================================+
   | RFC 2409              | Defines the IKE protocol, which negotiates and verifies key information to safeguard VPNs.                         | -  Use the pre-shared key (PSK) to reach an IKE peer agreement. |
   |                       |                                                                                                                    | -  Use the main mode for negotiation.                           |
   +-----------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
   | RFC 4301              | Defines the IPsec architecture, the security services that IPsec offers, and the collaboration between components. | Use the IPsec tunnel to set up a VPN connection.                |
   +-----------------------+--------------------------------------------------------------------------------------------------------------------+-----------------------------------------------------------------+
