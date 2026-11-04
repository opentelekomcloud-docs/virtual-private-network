:original_name: vpn_api_0162.html

.. _vpn_api_0162:

Exporting VPN Connection Configurations
=======================================

Function
--------

This API is used to export VPN connection configurations on a specified customer gateway device.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

POST /v5/{project_id}/vpn-connection/{vpn_connection_id}/peer-configuration/export

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

   .. table:: **Table 2** Request parameters

      ========= ====== ========= ===========================
      Parameter Type   Mandatory Description
      ========= ====== ========= ===========================
      vendor    String Yes       Specifies a vendor.
      type      String Yes       Specifies a device series.
      model     String Yes       Specifies a device model.
      version   String Yes       Specifies a device version.
      ========= ====== ========= ===========================

-  Example request

   .. code-block:: text

      POST https://{Endpoint}/v5/{project_id}/vpn-connection/{vpn_connection_id}/peer-configuration/export

      {
        "vendor": "vendor-name-1",
        "type": "type-1"
        "model": "model-1",
        "version": "1.0"
      }

Response
--------

-  Response parameters

   Returned status code 200: successful operation

   .. table:: **Table 3** Parameters in the response body

      =========== ====== ==============================
      Parameter   Type   Description
      =========== ====== ==============================
      request_id  String Specifies a request ID.
      peer_config String Specifies peer configurations.
      =========== ====== ==============================

-  Example response

   .. code-block::

      {
          "request_id": "e905df2f8ec9f68f1d8c53a692dc7eea",
          "peer_config": "the configuration information of the peer device"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
