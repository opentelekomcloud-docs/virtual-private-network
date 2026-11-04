:original_name: vpn_api_0163.html

.. _vpn_api_0163:

Obtaining On-premises Devices Whose VPN Connection Configurations Can Be Exported
=================================================================================

Function
--------

This API is used to obtain on-premises devices whose VPN connection configurations can be exported.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

GET /v5/{project_id}/peer-configuration/supported-devices

.. table:: **Table 1** Parameter description

   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter  | Type   | Mandatory | Description                                                                                                                           |
   +============+========+===========+=======================================================================================================================================+
   | project_id | String | Yes       | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +------------+--------+-----------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   None

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v5/{project_id}/peer-configuration/supported-devices

Response
--------

-  Response parameters

   Returned status code 200: successful operation

   .. table:: **Table 2** Parameters in the response body

      ================= ====================== ============================
      Parameter         Type                   Description
      ================= ====================== ============================
      request_id        String                 Specifies a request ID.
      supported_devices SupportedDevice Object Specifies supported devices.
      ================= ====================== ============================

   .. table:: **Table 3** SupportedDevice

      ========= ====== ===========================
      Parameter Type   Description
      ========= ====== ===========================
      vendor    String Specifies a vendor.
      type      String Specifies a device series.
      model     String Specifies a device model.
      version   String Specifies a device version.
      ========= ====== ===========================

-  Example response

   .. code-block::

      {
          "supported_devices": [
              {
                  "vendor": "vendor-name-1",
                  "type": "type-1",
                  "model": "model-1",
                  "version": "1.0"
              },
              {
                  "vendor": "vendor-name-2",
                  "type": "type-2",
                  "model": "model-2",
                  "version": "1.0"
              }
          ],
          "request_id": "44b94ae1f579e74526627b5a1a1a6428"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
