:original_name: vpn_api_0035.html

.. _vpn_api_0035:

Querying the List of VPN Connection Monitors
============================================

Function
--------

This API is used to query the list of VPN connection monitors.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

GET /v5/{project_id}/connection-monitors

.. table:: **Table 1** Parameter description

   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type   | Mandatory | Description                                                                                                                           |
   +============+========+===========+=======================================================================================================================================+
   | project_id | String | Yes       | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+

.. table:: **Table 2** Parameter in a query request

   +-----------------------+--------+-----------+-------------------------------------+
   | Parameter             | Type   | Mandatory | Description                         |
   +=======================+========+===========+=====================================+
   | vpn_connection_id     | String | No        | Specifies a VPN connection ID.      |
   +-----------------------+--------+-----------+-------------------------------------+
   | enterprise_project_id | Array  | No        | Specifies an enterprise project ID. |
   +-----------------------+--------+-----------+-------------------------------------+

Request
-------

-  Request parameters

   None

-  Example requests

   #. Query all VPN connection monitors.

      .. code-block:: text

         GET https://{Endpoint}/v5/{project_id}/connection-monitors

   #. Query VPN monitors based on a specified VPN connection ID.

      .. code-block:: text

         GET https://{Endpoint}/v5/{project_id}/connection-monitors?vpn_connection_id={vpn_connection_id}

Response
--------

-  Response parameters

   Returned status code 200: successful query

   .. table:: **Table 3** Parameters in the response body

      +---------------------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | Parameter           | Type                                                                                                                  | Description                              |
      +=====================+=======================================================================================================================+==========================================+
      | connection_monitors | Array of :ref:`ConnectionMonitorInfo <en-us_topic_0000001854169157__en-us_topic_0000001543354020_table72107>` objects | Specifies the connection_monitor object. |
      +---------------------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------+
      | request_id          | String                                                                                                                | Specifies a request ID.                  |
      +---------------------+-----------------------------------------------------------------------------------------------------------------------+------------------------------------------+

   .. _en-us_topic_0000001854169157__en-us_topic_0000001543354020_table72107:

   .. table:: **Table 4** ConnectionMonitorInfo

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
      |                       |                       | -  The value can only be **gateway**.                      |
      +-----------------------+-----------------------+------------------------------------------------------------+
      | source_ip             | String                | Specifies the source address to be monitored.              |
      +-----------------------+-----------------------+------------------------------------------------------------+
      | destination_ip        | String                | Specifies the destination address to be monitored.         |
      +-----------------------+-----------------------+------------------------------------------------------------+
      | proto_type            | String                | -  Specifies the protocol used by NQA.                     |
      |                       |                       | -  The value can only be **icmp**.                         |
      +-----------------------+-----------------------+------------------------------------------------------------+

-  Example responses

   #. Response to the request for querying all VPN connection monitors

      .. code-block::

         {
             "connection_monitors":[
                 {
                     "id":"76f64229-demo-a8df-va86-3907e2815b6d",
                     "status":"ACTIVE",
                     "vpn_connection_id":"2342adf2-demo-a8df-va86-12aq511s0917",
                     "type":"gateway",
                     "source_ip":"88.***.***.60",
                     "destination_ip":"88.***.***.32",
                     "proto_type":"icmp"
                 },
                 {
                     "id":"85t53318-demo-a8df-va86-zq9312525f6t",
                     "status":"ACTIVE",
                     "vpn_connection_id":"cae286f2-demo-a8df-va86-e22416ca1220",
                     "type":"gateway",
                     "source_ip":"89.***.***.21",
                     "destination_ip":"88.***.***.12",
                     "proto_type":"icmp"
                 }
             ],
             "request_id": "531f8b2c-ec55-45d8-90a3-ede922f7d63c"
         }

   #. Response to the request for querying monitors based on a specified VPN connection ID

      .. code-block::

         {
             "connection_monitors":[
                 {
                     "id":"76f64229-demo-a8df-va86-3907e2815b6d",
                     "status":"ACTIVE",
                     "vpn_connection_id":"2342adf2-demo-a8df-va86-12aq511s0917",
                     "type":"gateway",
                     "source_ip":"88.***.***.60",
                     "destination_ip":"88.***.***.32",
                     "proto_type":"icmp"
                 }
             ],
             "request_id": "05ab9b58-9b4c-4cee-8113-4b0f325f1dfc"
         }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
