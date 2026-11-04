:original_name: vpn_04_0702.html

.. _vpn_04_0702:

Metrics (S2C Enterprise Edition VPN)
====================================

Description
-----------

This section describes monitoring metrics reported by VPN to Cloud Eye as well as their namespaces and dimensions. You can use the Cloud Eye console or APIs to query the metrics of the monitored objects and alarms generated for VPN.

.. note::

   Cloud Eye supports a maximum of four dimension levels that are numbered from 0 to 3, with 3 representing the deepest level. For example, for the monitoring metric with the dimension **evpn_connection_id,evpn_sa_id**, dimensions **evpn_connection_id** and **evpn_sa_id** correspond to levels 0 and 1, respectively.

Namespace
---------

SYS.VPN

Metrics
-------

.. table:: **Table 1** Metrics supported for Enterprise Edition VPN gateways

   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+---------------+-----------------+-----------------+--------------------------------+
   | Metric ID               | Metric Name              | Description                                                   | Value Range | Unit          | Conversion Rule | Dimension       | Monitoring Interval (Raw Data) |
   +=========================+==========================+===============================================================+=============+===============+=================+=================+================================+
   | gateway_send_pkt_rate   | Outbound Packet Rate     | Average number of data packets leaving the cloud per second.  | >= 0        | pps           | N/A             | evpn_gateway_id | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+---------------+-----------------+-----------------+--------------------------------+
   | gateway_recv_pkt_rate   | Inbound Packet Rate      | Average number of data packets entering the cloud per second. | >= 0        | pps           | N/A             | evpn_gateway_id | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+---------------+-----------------+-----------------+--------------------------------+
   | gateway_send_rate       | Outbound Bandwidth       | Average volume of traffic leaving the cloud per second.       | 0-1         | bps           | 1024(IEC)       | evpn_gateway_id | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+---------------+-----------------+-----------------+--------------------------------+
   | gateway_recv_rate       | Inbound Bandwidth        | Average volume of traffic entering the cloud per second.      | 0-1         | bps           | 1024(IEC)       | evpn_gateway_id | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+---------------+-----------------+-----------------+--------------------------------+
   | gateway_send_rate_usage | Outbound Bandwidth Usage | Bandwidth utilization for traffic leaving the cloud.          | 0-100       | percentage(%) | N/A             | evpn_gateway_id | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+---------------+-----------------+-----------------+--------------------------------+
   | gateway_recv_rate_usage | Inbound Bandwidth Usage  | Bandwidth utilization for traffic entering the cloud.         | 0-100       | percentage(%) | N/A             | evpn_gateway_id | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+---------------+-----------------+-----------------+--------------------------------+
   | gateway_connection_num  | Number of Connections    | Number of VPN connections.                                    | >= 0        | count         | N/A             | evpn_gateway_id | 1 minute                       |
   +-------------------------+--------------------------+---------------------------------------------------------------+-------------+---------------+-----------------+-----------------+--------------------------------+

.. table:: **Table 2** Enterprise Edition VPN connection metrics

   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | Metric ID                                   | Metric Name             | Description                                                                                | Value Range | Unit          | Conversion Rule | Dimension                     | Monitoring Interval (Raw Data) |
   +=============================================+=========================+============================================================================================+=============+===============+=================+===============================+================================+
   | tunnel_average_latency                      | Average Tunnel RTT      | Average round-trip time on the tunnel between the VPN gateway and customer gateway.        | 0-5000      | ms            | N/A             | evpn_connection_id            | 10s                            |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | tunnel_max_latency                          | Maximum Tunnel RTT      | Maximum round-trip time on the tunnel between the VPN gateway and customer gateway.        | 0-5000      | ms            | N/A             | evpn_connection_id            | 10s                            |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | tunnel_packet_loss_rate                     | Tunnel Packet Loss Rate | Packet loss rate on the tunnel between the VPN gateway and customer gateway.               | 0-100       | percentage(%) | N/A             | evpn_connection_id            | 10s                            |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | link_average_latency                        | Average Link RTT        | Average round-trip time on the physical link between the VPN gateway and customer gateway. | 0-5000      | s             | N/A             | evpn_connection_id            | 10s                            |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | link_max_latency                            | Maximum Link RTT        | Maximum round-trip time on the physical link between the VPN gateway and customer gateway. | 0-5000      | ms            | N/A             | evpn_connection_id            | 10s                            |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | link_packet_loss_rate                       | Link Packet Loss Rate   | Packet loss rate on the physical link between the VPN gateway and customer gateway.        | 0-100       | percentage(%) | N/A             | evpn_connection_id            | 10s                            |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | connection_status                           | VPN Connection Status   | Status of a VPN connection:                                                                | 0, 1, or 2  | N/A           | N/A             | evpn_connection_id            | 1 minute                       |
   |                                             |                         |                                                                                            |             |               |                 |                               |                                |
   |                                             |                         | -  **0**: not connected                                                                    |             |               |                 |                               |                                |
   |                                             |                         | -  **1**: connected                                                                        |             |               |                 |                               |                                |
   |                                             |                         | -  **2**: unknown                                                                          |             |               |                 |                               |                                |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | recv_pkt_rate (deprecated, not recommended) | Packet Receive Rate     | Average number of data packets received per second.                                        | >= 0        | pps           | N/A             | evpn_connection_id            | 1 minute                       |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | send_pkt_rate (deprecated, not recommended) | Packet Send Rate        | Average number of data packets sent per second.                                            | >= 0        | pps           | N/A             | evpn_connection_id            | 1 minute                       |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | recv_rate (deprecated, not recommended)     | Traffic Receive Rate    | Average volume of traffic received per second.                                             | 0-1         | bps           | 1024(IEC)       | evpn_connection_id            | 1 minute                       |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | send_rate (deprecated, not recommended)     | Traffic Send Rate       | Average volume of traffic sent per second.                                                 | 0-1         | bps           | 1024(IEC)       | evpn_connection_id            | 1 minute                       |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | sa_send_pkt_rate                            | SA Packet Send Rate     | Average number of data packets sent over an SA per second.                                 | >= 0        | pps           | N/A             | evpn_connection_id,evpn_sa_id | 1 minute                       |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | sa_recv_pkt_rate                            | SA Packet Receive Rate  | Average number of data packets received over an SA per second.                             | >= 0        | pps           | N/A             | evpn_connection_id,evpn_sa_id | 1 minute                       |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | sa_recv_rate                                | SA Traffic Receive Rate | Average volume of traffic received over an SA per second.                                  | 0-1         | bps           | 1024(IEC)       | evpn_connection_id,evpn_sa_id | 1 minute                       |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+
   | sa_send_rate                                | SA Traffic Send Rate    | Average volume of traffic sent over an SA per second.                                      | 0-1         | bps           | 1024(IEC)       | evpn_connection_id,evpn_sa_id | 1 minute                       |
   +---------------------------------------------+-------------------------+--------------------------------------------------------------------------------------------+-------------+---------------+-----------------+-------------------------------+--------------------------------+

.. note::

   -  After a VPN gateway is upgraded to the latest version, the monitoring interval of the following metrics changes to 10 seconds. The actual monitoring interval is subject to that displayed on the management console.

      Average Tunnel RTT, Maximum Tunnel RTT, Tunnel Packet Loss Rate, Average Link RTT, Maximum Link RTT, and Link Packet Loss Rate

   -  The bandwidth utilization of the VPN service is calculated by dividing the actually consumed bandwidth by the total forwarding capacity of two devices. For example, if the active and standby VPN gateways of the Professional 2 specification each support 1000 Mbit/s, the denominator is 2000 Mbit/s. The actual denominator is subject to the VPN gateway bandwidth you purchased.

If a monitored object has multiple levels of dimensions, the dimensional hierarchy of specific metrics must be specified when you use APIs to query the metrics.

For example, assume that you need to query the metric **sa_send_pkt_rate**, which indicates the SA packet sending rate of a VPN connection. The dimension of this metric is **evpn_connection_id,evpn_sa_id**, where **evpn_connection_id** and **evpn_sa_id** correspond to levels 0 and 1, respectively.

-  When an API is used to query a metric of a single SA, the input dimension information is as follows:

   .. code-block::

      dim.0=evpn_connection_id,2C2291dde7-193f-4fb8-9606-40c31e147422&dim.1=evpn_sa_id,2C7965df5f-2e83-4d87-8681-78f69e6c4185

   2C2291dde7-193f-4fb8-9606-40c31e147422 and 2C7965df5f-2e83-4d87-8681-78f69e6c4185 are the values of dimensions **evpn_connection_id** and **evpn_sa_id**, respectively. For details about how to obtain dimension values, see :ref:`Dimensions <en-us_topic_0000001592773849__section1512885019588>`.

-  When an API is used to query a metric of multiple SAs in batches, the input dimension information is as follows:

   .. code-block::

      "dimensions": [
                       {
                           "name": "evpn_connection_id",
                           "value": "2C2291dde7-193f-4fb8-9606-40c31e147422"
                       },
                       {
                           "name": "evpn_sa_id",
                           "value": "2C7965df5f-2e83-4d87-8681-78f69e6c4185"
                       },
                       {
                           "name": "evpn_sa_id",
                           "value": "506afac2-1f95-4dad-a73a-a726ad125723"
                       }
                   ]

   2C2291dde7-193f-4fb8-9606-40c31e147422 is the value of dimension **evpn_connection_id**; 2C7965df5f-2e83-4d87-8681-78f69e6c4185 and 506afac2-1f95-4dad-a73a-a726ad125723 are the values of dimension **evpn_sa_id**. For details about how to obtain dimension values, see :ref:`Dimensions <en-us_topic_0000001592773849__section1512885019588>`.

.. _en-us_topic_0000001592773849__section1512885019588:

Dimensions
----------

================== ===================================================
key                Value
================== ===================================================
evpn_connection_id Enterprise Edition **S2C VPN** connection.
evpn_sa_id         SA of an Enterprise Edition **S2C VPN** connection.
evpn_gateway_id    Enterprise Edition **S2C VPN** gateway.
================== ===================================================
