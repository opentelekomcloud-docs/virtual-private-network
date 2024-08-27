:original_name: vpn_04_0702.html

.. _vpn_04_0702:

Metrics (Enterprise Edition VPN)
================================

Description
-----------

This section describes monitored metrics reported by VPN to Cloud Eye as well as their namespaces and dimensions. You can use the Cloud Eye management console to query the metrics of the monitored objects and alarms generated for VPN.

Namespace
---------

SYS.VPN

Metrics
-------

.. table:: **Table 1** Metrics supported for Enterprise Edition VPN gateways

   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | Metric ID               | Metric Name              | Description                                                   | Value Range | Monitored Object | Monitoring Interval (Raw Data) |
   +=========================+==========================+===============================================================+=============+==================+================================+
   | gateway_send_pkt_rate   | Outbound Packet Rate     | Average number of data packets leaving the cloud per second.  | >= 0 pps    | Gateway          | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | gateway_recv_pkt_rate   | Inbound Packet Rate      | Average number of data packets entering the cloud per second. | >= 0 pps    | Gateway          | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | gateway_send_rate       | Outbound Bandwidth       | Average volume of traffic leaving the cloud per second.       | 0-1 Gbit/s  | Gateway          | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | gateway_recv_rate       | Inbound Bandwidth        | Average volume of traffic entering the cloud per second.      | 0-1 Gbit/s  | Gateway          | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | gateway_send_rate_usage | Outbound Bandwidth Usage | Bandwidth utilization for traffic leaving the cloud.          | 0-100%      | Gateway          | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | gateway_recv_rate_usage | Inbound Bandwidth Usage  | Bandwidth utilization for traffic entering the cloud.         | 0-100%      | Gateway          | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+
   | gateway_connection_num  | Number of Connections    | Number of VPN connections.                                    | >= 0        | Gateway          | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+------------------+--------------------------------+

.. table:: **Table 2** Enterprise Edition VPN connection metrics

   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | Metric ID               | Metric Name             | Description                                                                                | Value Range | Monitored Object | Monitoring Interval (Raw Data) |
   +=========================+=========================+============================================================================================+=============+==================+================================+
   | tunnel_average_latency  | Average Tunnel RTT      | Average round-trip time on the tunnel between the VPN gateway and customer gateway.        | 0-5000 ms   | VPN connection   | 1 minute                       |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | tunnel_max_latency      | Maximum Tunnel RTT      | Maximum round-trip time on the tunnel between the VPN gateway and customer gateway.        | 0-5000 ms   | VPN connection   | 1 minute                       |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | tunnel_packet_loss_rate | Tunnel Packet Loss Rate | Packet loss rate on the tunnel between the VPN gateway and customer gateway.               | 0-100 %     | VPN connection   | 1 minute                       |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | link_average_latency    | Average Link RTT        | Average round-trip time on the physical link between the VPN gateway and customer gateway. | 0-5000 ms   | VPN connection   | 1 minute                       |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | link_max_latency        | Maximum Link RTT        | Maximum round-trip time on the physical link between the VPN gateway and customer gateway. | 0-5000 ms   | VPN connection   | 1 minute                       |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | link_packet_loss_rate   | Link Packet Loss Rate   | Packet loss rate on the physical link between the VPN gateway and customer gateway.        | 0-100 %     | VPN connection   | 1 minute                       |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | connection_status       | VPN Connection Status   | Status of a VPN connection:                                                                | 0, 1, or 2  | VPN connection   | 1 minute                       |
   |                         |                         |                                                                                            |             |                  |                                |
   |                         |                         | **0**: not connected                                                                       |             |                  |                                |
   |                         |                         |                                                                                            |             |                  |                                |
   |                         |                         | **1**: connected                                                                           |             |                  |                                |
   |                         |                         |                                                                                            |             |                  |                                |
   |                         |                         | **2**: unknown                                                                             |             |                  |                                |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | recv_pkt_rate           | Packet Receive Rate     | Average number of data packets received per second.                                        | >= 0 pps    | VPN connection   | 1 minute                       |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | send_pkt_rate           | Packet Send Rate        | Average number of data packets sent per second.                                            | >= 0 pps    | VPN connection   | 1 minute                       |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | recv_rate               | Traffic Receive Rate    | Average volume of traffic received per second.                                             | 0~1Gbit/s   | VPN connection   | 1 minute                       |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+
   | send_rate               | Traffic Send Rate       | Average volume of traffic sent per second.                                                 | 0~1Gbit/s   | VPN connection   | 1 minute                       |
   +-------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+------------------+--------------------------------+

Dimensions
----------

================== =================================
key                Value
================== =================================
evpn_connection_id Enterprise Edition VPN connection
evpn_gateway_id    Enterprise Edition VPN gateway
================== =================================
