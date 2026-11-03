:original_name: vpn_api_0031.html

.. _vpn_api_0031:

Deleting a VPN Connection
=========================

Function
--------

This API is used to delete a VPN connection with a specified connection ID.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

DELETE /v5/{project_id}/vpn-connection/{vpn_connection_id}

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

      DELETE https://{Endpoint}/v5/{project_id}/vpn-connection/{vpn_connection_id}

Response
--------

-  Response parameters

   Returned status code 204: successful deletion

-  Example response

   Response returned when a frozen VPN connection fails to be deleted

   .. code-block:: text

      DELETE https://{Endpoint}/v5/{project_id}/vpn-connection/{vpn_connection_id}

      {
          "error_code":"VPN.0001",
          "error_msg":"invalid request: ILLEGAL not allowed delete vpnConnection",
          "request_id":"76b771cb-3b2a-151a-5bed-fdf5df12ff82"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
