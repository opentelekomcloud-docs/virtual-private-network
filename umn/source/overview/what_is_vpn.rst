:original_name: en-us_topic_0035391393.html

.. _en-us_topic_0035391393:

What Is VPN?
============

Overview
--------

Virtual Private Network (VPN) establishes secure, reliable, and cost-effective encrypted connections between your on-premises network or data center and a virtual network on the cloud.

.. note::

   VPN supports only non-cross-border connections.

-  A VPN gateway provides an Internet egress for a Virtual Private Cloud (VPC) to connect to a customer gateway in your on-premises data center.
-  A VPN connection connects a VPN gateway to a customer gateway through encrypted tunnels, enabling communication between a VPC and your on-premises data center. This helps quickly establish a secure hybrid cloud environment.

:ref:`Figure 1 <en-us_topic_0000001937647830__en-us_topic_0000001923184333_fig1268374311223>` shows the VPN networking.

.. _en-us_topic_0000001937647830__en-us_topic_0000001923184333_fig1268374311223:

.. figure:: /_static/images/en-us_image_0000001877145402.png
   :alt: **Figure 1** VPN networking

   **Figure 1** VPN networking

Components
----------

-  **VPN gateway**: a virtual gateway of VPN on the cloud. It establishes secure private connections with a customer gateway in your on-premises network or data center.
-  **Customer gateway**: a resource that provides information to the cloud about your customer gateway device. It can be a physical device or software application in your on-premises data center.
-  **VPN connection**: a secure channel between a VPN gateway and a customer gateway. VPN connections use the Internet Key Exchange (IKE) and IPsec protocols to encrypt the transmitted data.
