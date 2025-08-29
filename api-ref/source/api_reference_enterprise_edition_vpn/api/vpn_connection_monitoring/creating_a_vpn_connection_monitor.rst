:original_name: vpn_api_0033.html

.. _vpn_api_0033:

Creating a VPN Connection Monitor
=================================

Function
--------

This API is used to create a VPN connection monitor to perform health check between gateways. After a VPN connection monitor is created, the VPN gateway sends probe packets to the customer gateway to collect statistics about the round-trip delay and packet loss rate, thereby monitoring quality of VPN connections between the gateways.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

POST /v5/{project_id}/connection-monitors

.. table:: **Table 1** Parameter description

   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type   | Mandatory | Description                                                                                                                           |
   +============+========+===========+=======================================================================================================================================+
   | project_id | String | Yes       | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   .. table:: **Table 2** Request parameters

      +--------------------+---------------------------------------------------------------------------------------------------------------------------------+-----------+------------------------------------------+
      | Parameter          | Type                                                                                                                            | Mandatory | Description                              |
      +====================+=================================================================================================================================+===========+==========================================+
      | connection_monitor | :ref:`CreateConnectionMonitorRequestBodyContent <en-us_topic_0000001807530304__en-us_topic_0000001543513464_table72095>` object | Yes       | Specifies the connection_monitor object. |
      +--------------------+---------------------------------------------------------------------------------------------------------------------------------+-----------+------------------------------------------+

   .. _en-us_topic_0000001807530304__en-us_topic_0000001543513464_table72095:

   .. table:: **Table 3** CreateConnectionMonitorRequestBodyContent

      +-------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------+
      | Parameter         | Type            | Mandatory       | Description                                                                                                  |
      +===================+=================+=================+==============================================================================================================+
      | vpn_connection_id | String          | Yes             | Specifies the ID of the VPN connection to be monitored.                                                      |
      |                   |                 |                 |                                                                                                              |
      |                   |                 |                 | You can obtain VPN connection IDs by :ref:`querying the VPN connection list <en-us_topic_0000001807530300>`. |
      +-------------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      POST https://{Endpoint}/v5/{project_id}/connection-monitors

      {
          "connection_monitor": {
              "vpn_connection_id": "cae286f2-demo-a8df-va86-e22416ca1220"
          }
      }

Response
--------

-  Response parameters

   Returned status code 201: successful operation

   .. table:: **Table 4** Parameters in the response body

      +--------------------+-------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Parameter          | Type                                                                                                        | Description                              |
      +====================+=============================================================================================================+==========================================+
      | connection_monitor | :ref:`ConnectionMonitorInfo <en-us_topic_0000001807530304__en-us_topic_0000001543513464_table72097>` object | Specifies the connection_monitor object. |
      +--------------------+-------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | request_id         | String                                                                                                      | Specifies a request ID.                  |
      +--------------------+-------------------------------------------------------------------------------------------------------------+------------------------------------------+

   .. _en-us_topic_0000001807530304__en-us_topic_0000001543513464_table72097:

   .. table:: **Table 5** ConnectionMonitorInfo

      +-----------------------+-----------------------+------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                |
      +=======================+=======================+============================================================+
      | id                    | String                | -  Specifies the ID of a VPN connection monitor.           |
      |                       |                       | -  The value is a UUID containing 36 characters.           |
      +-----------------------+-----------------------+------------------------------------------------------------+
      | vpn_connection_id     | String                | -  Specifies the ID of the VPN connection to be monitored. |
      |                       |                       | -  The value is a UUID containing 36 characters.           |
      +-----------------------+-----------------------+------------------------------------------------------------+
      | type                  | String                | -  Specifies the type of objects to be monitored.          |
      |                       |                       |                                                            |
      |                       |                       | -  Value range:                                            |
      |                       |                       |                                                            |
      |                       |                       |    **gateway**: VPN gateway                                |
      +-----------------------+-----------------------+------------------------------------------------------------+
      | source_ip             | String                | Specifies the source address to be monitored.              |
      +-----------------------+-----------------------+------------------------------------------------------------+
      | destination_ip        | String                | Specifies the destination address to be monitored.         |
      +-----------------------+-----------------------+------------------------------------------------------------+
      | proto_type            | String                | -  Specifies the protocol used by NQA.                     |
      |                       |                       |                                                            |
      |                       |                       | -  Value range:                                            |
      |                       |                       |                                                            |
      |                       |                       |    **icmp**: ICMP protocol                                 |
      +-----------------------+-----------------------+------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "connection_monitor":{
              "id":"76f64229-demo-a8df-va86-3907e2815b6d",
              "vpn_connection_id":"cae286f2-demo-a8df-va86-e22416ca1220",
              "type":"gateway",
              "source_ip":"88.***.***.60",
              "destination_ip":"88.***.***.32",
              "proto_type":"icmp"
          },
          "request_id": "bd37d16d-387c-41ab-a180-01b649f73590"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
