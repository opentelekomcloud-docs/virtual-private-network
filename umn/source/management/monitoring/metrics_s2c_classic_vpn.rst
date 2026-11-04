:original_name: vpn_04_0705.html

.. _vpn_04_0705:

Metrics (S2C Classic VPN)
=========================

Description
-----------

This section describes monitoring metrics reported by VPN to Cloud Eye as well as their namespaces and dimensions. You can use the Cloud Eye console to query the metrics of the monitored objects and alarms generated for VPN.

Namespace
---------

SYS.VPC

Metrics
-------

.. table:: **Table 1** Metrics supported for Classic VPN connections

   +-------------------+-----------------------+-----------------------------+-------------+--------+-----------------+-------------------+--------------------------------+
   | Metric ID         | Metric Name           | Description                 | Value Range | Unit   | Conversion Rule | Dimension         | Monitoring Interval (Raw Data) |
   +===================+=======================+=============================+=============+========+=================+===================+================================+
   | connection_status | VPN Connection Status | Status of a VPN connection: | 0 or 1      | N/A    | N/A             | vpn_connection_id | 5 minutes                      |
   |                   |                       |                             |             |        |                 |                   |                                |
   |                   |                       | -  **0**: not connected     |             |        |                 |                   |                                |
   |                   |                       | -  **1**: connected         |             |        |                 |                   |                                |
   +-------------------+-----------------------+-----------------------------+-------------+--------+-----------------+-------------------+--------------------------------+

Dimensions
----------

================= ===========================
key               Value
================= ===========================
vpn_connection_id S2C Classic VPN connection.
================= ===========================
