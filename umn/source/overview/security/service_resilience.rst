:original_name: vpn_01_0023.html

.. _vpn_01_0023:

Service Resilience
==================

VPN provides the dual-AZ disaster recovery function. You can create a VPN gateway in two AZs in the same region, and create a VPN connection between the customer gateway and each AZ.


.. figure:: /_static/images/en-us_image_0000002402149549.png
   :alt: **Figure 1** Scenario where services are running properly

   **Figure 1** Scenario where services are running properly

If the VPN gateway or VPN connection in an AZ is faulty, traffic is automatically switched to the other VPN connection, ensuring normal service running.


.. figure:: /_static/images/en-us_image_0000002402109921.png
   :alt: **Figure 2** Failover scenario

   **Figure 2** Failover scenario
