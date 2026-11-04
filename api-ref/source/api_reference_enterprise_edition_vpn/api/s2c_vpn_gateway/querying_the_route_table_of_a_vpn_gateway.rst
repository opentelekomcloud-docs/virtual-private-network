:original_name: vpn_api_0144.html

.. _vpn_api_0144:

Querying the Route Table of a VPN Gateway
=========================================

Function
--------

This API is used to query the route table of a VPN gateway with a specified ID.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

GET /v5/{project_id}/vpn-gateways/{vgw_id}/routing-table

.. table:: **Table 1** Parameter description

   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type   | Mandatory | Description                                                                                                                           |
   +============+========+===========+=======================================================================================================================================+
   | project_id | String | Yes       | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | vgw_id     | String | Yes       | Specifies a VPN gateway ID.                                                                                                           |
   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   None

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v5/{project_id}/vpn-gateways/{vgw_id}/routing-table

Response
--------

-  Response parameters

   Returned status code 200: successful query

   .. table:: **Table 2** Parameters in the response body

      +---------------+----------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
      | Parameter     | Type                                                                                                           | Description                                           |
      +===============+================================================================================================================+=======================================================+
      | routing_table | Array of :ref:`Route <en-us_topic_0000002541824368__en-us_topic_0000002130273825_table15658192183913>` objects | Indicates the route table of a specified VPN gateway. |
      +---------------+----------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
      | total_count   | Long                                                                                                           | Specifies the total number of routes on the gateway.  |
      +---------------+----------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+
      | page_info     | :ref:`ResponsePageInfoV3 <en-us_topic_0000002541824368__en-us_topic_0000002130273825_table459554404>` object   | Specifies pagination information.                     |
      +---------------+----------------------------------------------------------------------------------------------------------------+-------------------------------------------------------+

   .. _en-us_topic_0000002541824368__en-us_topic_0000002130273825_table15658192183913:

   .. table:: **Table 3** Route

      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | Parameter             | Type                                                                                                          | Description                                              |
      +=======================+===============================================================================================================+==========================================================+
      | destination           | String                                                                                                        | Specifies the destination address of a route.            |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | nexthop               | String                                                                                                        | Specifies the next-hop IP address.                       |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | outbound_interface_ip | String                                                                                                        | Specifies the IP address of the outbound interface.      |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | origin                | String                                                                                                        | -  Specifies the origin of a BGP route.                  |
      |                       |                                                                                                               | -  The value can be **igp**, **egp**, or **incomplete**. |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | as_path               | String                                                                                                        | Specifies the AS_Path of a BGP route.                    |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | med                   | Integer                                                                                                       | Specifies the MED value of a BGP route.                  |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+
      | nexthop_resource      | :ref:`NexthopResource <en-us_topic_0000002541824368__en-us_topic_0000002130273825_table1531518135534>` object | Specifies the next hop resource of a route.              |
      +-----------------------+---------------------------------------------------------------------------------------------------------------+----------------------------------------------------------+

   .. _en-us_topic_0000002541824368__en-us_topic_0000002130273825_table1531518135534:

   .. table:: **Table 4** NexthopResource

      +-----------------------+-----------------------+--------------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                        |
      +=======================+=======================+====================================================================+
      | id                    | String                | Specifies the next-hop resource ID, which is in UUID format.       |
      +-----------------------+-----------------------+--------------------------------------------------------------------+
      | type                  | String                | -  Specifies the next-hop resource type.                           |
      |                       |                       | -  The value can be **er**, **vpn_gateway** or **vpn_connection**. |
      +-----------------------+-----------------------+--------------------------------------------------------------------+

   .. _en-us_topic_0000002541824368__en-us_topic_0000002130273825_table459554404:

   .. table:: **Table 5** ResponsePageInfoV3

      ============= ======= ================================================
      Parameter     Type    Description
      ============= ======= ================================================
      current_count Integer Specifies the number of resources in the list.
      next_marker   String  Specifies the **marker** value of the next page.
      ============= ======= ================================================

-  Example response

   #. Example response to the request for querying a public VPN gateway associated with an enterprise router

      .. code-block::

         {
             "routing_table": [
                 {
                     "destination": "192.168.0.0/24",
                     "nexthop": "192.168.0.240",
                     "outbound_interface_ip": "192.168.0.240",
                     "origin": "igp",
                     "as_path": "64513",
                     "med": 0,
                     "nexthop_resource": {
                         "id": "fd8e4220-cdcd-4c84-809e-09fd3148b24b",
                         "type": "vpn_connection"
                     }
                 },
                 {
                     "destination": "222.69.222.1/32",
                     "nexthop": "169.254.1.2",
                     "outbound_interface_ip": "169.254.1.1",
                     "origin": "igp",
                     "as_path": "64513",
                     "med": 0,
                     "nexthop_resource": {
                         "id": "e3c28cc1-fb34-4acd-97f9-29d8e42efe0f",
                         "type": "vpn_gateway"
                     }
                 },
                 {
                     "destination": "222.69.222.2/32",
                     "nexthop": "169.254.2.2",
                     "outbound_interface_ip": "169.254.2.1",
                     "origin": "igp",
                     "as_path": "64513",
                     "med": 0,
                     "nexthop_resource": {
                         "id": "85d31993-f519-49ea-8d2e-7afeffb8ef5e",
                         "type": "vpn_connection"
                     }
                 }
             ],
             "total_count": 3,
             "page_info": {
                 "current_count": 3
             }
         }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
