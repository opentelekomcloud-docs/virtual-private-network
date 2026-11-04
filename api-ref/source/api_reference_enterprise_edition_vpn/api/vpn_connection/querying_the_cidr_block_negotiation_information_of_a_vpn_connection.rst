:original_name: vpn_api_0165.html

.. _vpn_api_0165:

Querying the CIDR Block Negotiation Information of a VPN Connection
===================================================================

Function
--------

This API is used to query the CIDR block negotiation information of a VPN connection based on the specified connection ID.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

GET /v5/{project_id}/vpn-connection/{vpn_connection_id}/ipsec-sa

.. table:: **Table 1** Parameter description

   +-------------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter         | Type   | Mandatory | Description                                                                                                                           |
   +===================+========+===========+=======================================================================================================================================+
   | project_id        | String | Yes       | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +-------------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | vpn_connection_id | String | Yes       | Specifies a VPN connection ID.                                                                                                        |
   +-------------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   None

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v5/{project_id}/vpn-connection/{vpn_connection_id}/ipsec-sa

Response
--------

-  Response parameters

   Returned status code 200: successful operation

   .. table:: **Table 2** Parameters in the response body

      +------------+----------------------------------------------------------------------------------------------------------------+------------------------------+
      | Parameter  | Type                                                                                                           | Description                  |
      +============+================================================================================================================+==============================+
      | request_id | String                                                                                                         | Specifies a request ID.      |
      +------------+----------------------------------------------------------------------------------------------------------------+------------------------------+
      | sa_infos   | Array of :ref:`SaInfo <en-us_topic_0000002572264683__en-us_topic_0000002537831974_table1898011410196>` objects | Specifies the SaInfo object. |
      +------------+----------------------------------------------------------------------------------------------------------------+------------------------------+

   .. _en-us_topic_0000002572264683__en-us_topic_0000002537831974_table1898011410196:

   .. table:: **Table 3** SaInfo

      +-----------------------+-----------------------+-------------------------------------------------------+
      | Parameter             | Type                  | Description                                           |
      +=======================+=======================+=======================================================+
      | id                    | String                | Specifies the CIDR block negotiation ID.              |
      +-----------------------+-----------------------+-------------------------------------------------------+
      | source_ip_cidr        | String                | Specifies the source CIDR block.                      |
      +-----------------------+-----------------------+-------------------------------------------------------+
      | dest_ip_cidr          | String                | Specifies the destination CIDR block.                 |
      +-----------------------+-----------------------+-------------------------------------------------------+
      | packets_sent          | Integer               | Specifies the number of packets sent.                 |
      +-----------------------+-----------------------+-------------------------------------------------------+
      | packets_recv          | Integer               | Specifies the number of packets received.             |
      +-----------------------+-----------------------+-------------------------------------------------------+
      | traffic_sent          | Integer               | Specifies the number of bytes sent.                   |
      +-----------------------+-----------------------+-------------------------------------------------------+
      | traffic_recv          | Integer               | Specifies the number of bytes received.               |
      +-----------------------+-----------------------+-------------------------------------------------------+
      | collected_at          | String                | -  Specifies the data collection time.                |
      |                       |                       | -  The UTC time format is *yyyy-MM-ddTHH:mm:ss.SSSZ*. |
      +-----------------------+-----------------------+-------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "sa_infos": [
              {
                  "id": "4f43df63-9263-4895-ba15-e9aae9c9fa68",
                  "source_ip_cidr": "0.0.0.0/0",
                  "dest_ip_cidr": "0.0.0.0/0",
                  "packets_sent": 15516,
                  "packets_recv": 15513,
                  "traffic_sent": 1295454,
                  "traffic_recv": 1294979,
                  "collected_at": "2026-04-09T03:28:33.351Z"
              }
          ],
          "request_id": "61593611ee016546ba0a61992083d80b"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
