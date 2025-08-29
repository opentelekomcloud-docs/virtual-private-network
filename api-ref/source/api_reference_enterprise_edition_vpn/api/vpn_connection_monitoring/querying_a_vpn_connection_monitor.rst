:original_name: vpn_api_0034.html

.. _vpn_api_0034:

Querying a VPN Connection Monitor
=================================

Function
--------

This API is used to query a VPN connection monitor with a specified ID.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

GET /v5/{project_id}/connection-monitors/{connection_monitor_id}

.. table:: **Table 1** Parameter description

   +-----------------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type   | Mandatory | Description                                                                                                                           |
   +=======================+========+===========+=======================================================================================================================================+
   | project_id            | String | Yes       | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +-----------------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | connection_monitor_id | String | Yes       | Specifies the ID of a VPN connection monitor.                                                                                         |
   +-----------------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   None

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v5/{project_id}/connection-monitors/{connection_monitor_id}

Response
--------

-  Response parameters

   Returned status code 200: successful query

   .. table:: **Table 2** Parameters in the response body

      +--------------------+-------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Parameter          | Type                                                                                                        | Description                              |
      +====================+=============================================================================================================+==========================================+
      | connection_monitor | :ref:`ConnectionMonitorInfo <en-us_topic_0000001807370480__en-us_topic_0000001594472957_table72123>` object | Specifies the connection_monitor object. |
      +--------------------+-------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | request_id         | String                                                                                                      | Specifies a request ID.                  |
      +--------------------+-------------------------------------------------------------------------------------------------------------+------------------------------------------+

   .. _en-us_topic_0000001807370480__en-us_topic_0000001594472957_table72123:

   .. table:: **Table 3** ConnectionMonitorInfo

      +-----------------------+-----------------------+------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                |
      +=======================+=======================+============================================================+
      | id                    | String                | -  Specifies the ID of a VPN connection monitor.           |
      |                       |                       | -  The value is a UUID containing 36 characters.           |
      +-----------------------+-----------------------+------------------------------------------------------------+
      | status                | String                | -  Specifies the status of the VPN connection monitor.     |
      |                       |                       |                                                            |
      |                       |                       | -  Value range:                                            |
      |                       |                       |                                                            |
      |                       |                       |    **ACTIVE**: normal                                      |
      |                       |                       |                                                            |
      |                       |                       |    **PENDING_CREATE**: creating                            |
      |                       |                       |                                                            |
      |                       |                       |    **PENDING_DELETE**: deleting                            |
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
          "connection_monitor": {
              "id": "76f64229-demo-a8df-va86-3907e2815b6d",
              "status": "ACTIVE",
              "vpn_connection_id": "cae286f2-demo-a8df-va86-e22416ca1220",
              "type": "gateway",
              "source_ip": "88.***.***.60",
              "destination_ip": "88.***.***.32",
              "proto_type": "icmp"
          },
          "request_id": "6d212bc0-ecb1-457b-977b-5e815fce658d"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
