:original_name: vpn_api_0156.html

.. _vpn_api_0156:

Resetting a VPN Connection
==========================

Function
--------

This API is used to reset a VPN connection with a specified connection ID.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

POST /v5/{project_id}/vpn-connection/{vpn_connection_id}/reset

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

      POST https://{Endpoint}/v5/{project_id}/vpn-connection/{vpn_connection_id}/reset

Response
--------

-  Response parameters

   Returned status code 200: successful operation

   .. table:: **Table 2** Parameters in the response body

      ========== ====== =======================
      Parameter  Type   Description
      ========== ====== =======================
      request_id String Specifies a request ID.
      ========== ====== =======================

-  Example response

   .. code-block::

      {
        "request_id": "c63d850876bcddbdfbd11776cce57914"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
