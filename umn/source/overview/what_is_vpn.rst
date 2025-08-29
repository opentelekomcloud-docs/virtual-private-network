:original_name: vpn_01_0031.html

.. _vpn_01_0031:

What Is VPN?
============

Overview
--------

Virtual Private Network (VPN) establishes secure, reliable, and cost-effective encrypted connections between your on-premises network or data center and a virtual network on the cloud.

.. note::

   VPN supports only non-inter-border connections.

Site-to-Cloud VPN (S2C VPN) uses the Internet Protocol Security (IPsec) protocol and has two editions: Classic VPN and Enterprise Edition VPN.

S2C VPN involves three key components: VPN gateway, customer gateway, and VPN connection.

-  A VPN gateway provides an Internet egress for a Virtual Private Cloud (VPC) to connect to a customer gateway in your on-premises data center.
-  A VPN connection connects a VPN gateway to a customer gateway through encrypted tunnels, enabling communication between a VPC and your on-premises data center. This helps quickly establish a secure hybrid cloud environment.

:ref:`Figure 1 <en-us_topic_0000001923184333__fig46751604918>` shows the VPN networking.

.. _en-us_topic_0000001923184333__fig46751604918:

.. figure:: /_static/images/en-us_image_0000002280894042.png
   :alt: **Figure 1** VPN networking

   **Figure 1** VPN networking

Components
----------

-  **VPN gateway**: a virtual gateway of VPN on the cloud. It establishes secure private connections with a customer gateway in your on-premises network or data center.
-  **Customer gateway**: a resource that provides information to the cloud about your customer gateway device. It can be a physical device or software application in your on-premises data center.
-  **VPN connection**: a secure channel between a VPN gateway and a customer gateway. VPN connections use the Internet Key Exchange (IKE) and IPsec protocols to encrypt the transmitted data.
