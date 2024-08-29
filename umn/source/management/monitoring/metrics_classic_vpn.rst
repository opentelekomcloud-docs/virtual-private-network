:original_name: vpn_04_0705.html

.. _vpn_04_0705:

Metrics (Classic VPN)
=====================

Description
-----------

This section describes monitored metrics reported by VPN to Cloud Eye as well as their namespaces and dimensions. You can use the Cloud Eye management console to query the metrics of the monitored objects and alarms generated for VPN.

Namespace
---------

SYS.VPC

Metrics
-------

.. table:: **Table 1** Metrics supported for Classic VPN bandwidth

   +----------------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | Metric ID                  | Metric Name              | Description                                                                                                                                                                                  | Value Range | Monitored Object | Monitoring Interval (Raw Data) |
   +============================+==========================+==============================================================================================================================================================================================+=============+==================+================================+
   | upstream_bandwidth         | Outbound Bandwidth       | Network rate of outbound traffic (previously called "Upstream Bandwidth").                                                                                                                   | >= 0 bit/s  | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                                                                                                                                              |             |                  |                                |
   |                            |                          | Unit: bit/s                                                                                                                                                                                  |             |                  |                                |
   +----------------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | downstream_bandwidth       | Inbound Bandwidth        | Network rate of inbound traffic (previously called "Downstream Bandwidth").                                                                                                                  | >= 0 bit/s  | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                                                                                                                                              |             |                  |                                |
   |                            |                          | Unit: bit/s                                                                                                                                                                                  |             |                  |                                |
   +----------------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | upstream_bandwidth_usage   | Outbound Bandwidth Usage | Usage of outbound bandwidth, in percentage.                                                                                                                                                  | 0-100%      | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                                                                                                                                              |             |                  |                                |
   |                            |                          | Outbound bandwidth usage = Outbound bandwidth/Purchased bandwidth                                                                                                                            |             |                  |                                |
   +----------------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | downstream_bandwidth_usage | Inbound Bandwidth Usage  | Usage of inbound bandwidth, in percentage.                                                                                                                                                   | 0-100%      | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                                                                                                                                              |             |                  |                                |
   |                            |                          | Inbound bandwidth usage = Inbound bandwidth/Purchased bandwidth                                                                                                                              |             |                  |                                |
   |                            |                          |                                                                                                                                                                                              |             |                  |                                |
   |                            |                          | .. note::                                                                                                                                                                                    |             |                  |                                |
   |                            |                          |                                                                                                                                                                                              |             |                  |                                |
   |                            |                          |    -  Up to 10 Mbit/s inbound bandwidth is provided for some sites that purchase an inbound bandwidth of less than 10 Mbit/s. As such, the inbound bandwidth usage may be greater than 100%. |             |                  |                                |
   |                            |                          |    -  If you change the bandwidth of an EIP in use, there is a delay of 5-10 minutes for the metrics to update for the new bandwidth.                                                        |             |                  |                                |
   +----------------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | up_stream                  | Outbound Traffic         | Outbound network traffic (previously called "Upstream Traffic")                                                                                                                              | >= 0 bytes  | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                                                                                                                                              |             |                  |                                |
   |                            |                          | Unit: byte                                                                                                                                                                                   |             |                  |                                |
   +----------------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | down_stream                | Inbound Traffic          | Inbound network traffic (previously called "Downstream Traffic")                                                                                                                             | >= 0 bytes  | Bandwidth or EIP | 1 minute                       |
   |                            |                          |                                                                                                                                                                                              |             |                  |                                |
   |                            |                          | Unit: byte                                                                                                                                                                                   |             |                  |                                |
   +----------------------------+--------------------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+

.. table:: **Table 2** Metrics supported for Classic VPN connections

   +-------------------+-----------------------+-----------------------------+-------------+------------------+--------------------------------+
   | Metric ID         | Metric Name           | Description                 | Value Range | Monitored Object | Monitoring Interval (Raw Data) |
   +===================+=======================+=============================+=============+==================+================================+
   | connection_status | VPN Connection Status | Status of a VPN connection: | 0 or 1      | VPN connection   | 5 minutes                      |
   |                   |                       |                             |             |                  |                                |
   |                   |                       | **0**: not connected        |             |                  |                                |
   |                   |                       |                             |             |                  |                                |
   |                   |                       | **1**: connected            |             |                  |                                |
   +-------------------+-----------------------+-----------------------------+-------------+------------------+--------------------------------+

Dimensions
----------

================= ===============
key               Value
================= ===============
vpn_connection_id VPN Connections
================= ===============
