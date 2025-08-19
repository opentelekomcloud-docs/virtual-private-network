:original_name: vpn_api_0145.html

.. _vpn_api_0145:

Querying VPN Connection Logs
============================

Function
--------

This API is used to query logs of a VPN connection with a specified connection ID.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

GET /v5/{project_id}/vpn-connection/{vpn_connection_id}/log

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

      GET https://{Endpoint}/v5/{project_id}/vpn-connection/{vpn_connection_id}/log

Response
--------

-  Response parameters

   Returned status code 200: successful operation

   .. table:: **Table 2** Parameters in the response body

      +------------+-----------------------------------------------------------------------------------------------------+---------------------------+
      | Parameter  | Type                                                                                                | Description               |
      +============+=====================================================================================================+===========================+
      | logs       | Array of :ref:`Log <en-us_topic_0000002343850520__en-us_topic_0000002163291185_table92830>` objects | Specifies the log object. |
      +------------+-----------------------------------------------------------------------------------------------------+---------------------------+
      | request_id | String                                                                                              | Specifies a request ID.   |
      +------------+-----------------------------------------------------------------------------------------------------+---------------------------+

   .. _en-us_topic_0000002343850520__en-us_topic_0000002163291185_table92830:

   .. table:: **Table 3** Log

      +-----------------------+-----------------------+-------------------------------+
      | Parameter             | Type                  | Description                   |
      +=======================+=======================+===============================+
      | time                  | Integer               | -  Specifies the timestamp.   |
      +-----------------------+-----------------------+-------------------------------+
      | raw_message           | String                | -  Specifies log information. |
      +-----------------------+-----------------------+-------------------------------+

-  Example response

   .. code-block::

      {
          "logs": [
              {
                  "time": 1735024112,
                  "raw_message": "2024-12-24T07:08:32.730275+00:00 host-xx-xx-xx-xx ipsec_ike[30085]: [xx.xx.xx.xx] IPSec tunnel negotiation fails. (IfIndex=[207], PolicyName=[], SeqNum=[0], PeerAddress=[xx.xx.xx.xx], PeerPort=[500], Reason=[version mismatch])"
              }
          ],
          "request_id": "f15d2c621593f2018c23eb1d49e3605e"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
