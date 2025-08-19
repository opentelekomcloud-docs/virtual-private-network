:original_name: vpn_api_0019.html

.. _vpn_api_0019:

.. _en-us_topic_0000001854089185:

Querying the AZs of VPN Gateways
================================

Function
--------

This API is used to query the AZs of VPN gateways.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

GET /v5/{project_id}/vpn-gateways/availability-zones

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

      GET https://{Endpoint}/v5/{project_id}/vpn-gateways/availability-zones

Response
--------

-  Response parameters

   Returned status code 200: successful operation

   .. table:: **Table 2** Parameters in the response body

      +--------------------+---------------------------------------------------------------------------------------------------------+----------------------------+
      | Parameter          | Type                                                                                                    | Description                |
      +====================+=========================================================================================================+============================+
      | availability_zones | :ref:`AvailabilityZones <en-us_topic_0000001854089185__en-us_topic_0000001543354004_table72053>` object | Specifies the list of AZs. |
      +--------------------+---------------------------------------------------------------------------------------------------------+----------------------------+
      | request_id         | String                                                                                                  | Specifies a request ID.    |
      +--------------------+---------------------------------------------------------------------------------------------------------+----------------------------+

   .. _en-us_topic_0000001854089185__en-us_topic_0000001543354004_table72053:

   .. table:: **Table 3** AvailabilityZones

      +--------------------------+-------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
      | Parameter                | Type                                                                                                              | Description                                                                   |
      +==========================+===================================================================================================================+===============================================================================+
      | basic                    | :ref:`VpnGatewayAvailabilityZones <en-us_topic_0000001854089185__en-us_topic_0000001543354004_table72054>` object | Indicates that the specification of VPN gateways is Basic.                    |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
      | professional1            | :ref:`VpnGatewayAvailabilityZones <en-us_topic_0000001854089185__en-us_topic_0000001543354004_table72054>` object | Indicates that the specification of VPN gateways is Professional1.            |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
      | Professional1-NonFixedIP | :ref:`VpnGatewayAvailabilityZones <en-us_topic_0000001854089185__en-us_topic_0000001543354004_table72054>` object | Indicates that the specification of VPN gateways is Professional1-NonFixedIP. |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
      | professional2            | :ref:`VpnGatewayAvailabilityZones <en-us_topic_0000001854089185__en-us_topic_0000001543354004_table72054>` object | Indicates that the specification of VPN gateways is Professional2.            |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+
      | Professional2-NonFixedIP | :ref:`VpnGatewayAvailabilityZones <en-us_topic_0000001854089185__en-us_topic_0000001543354004_table72054>` object | Indicates that the specification of VPN gateways is Professional2-NonFixedIP. |
      +--------------------------+-------------------------------------------------------------------------------------------------------------------+-------------------------------------------------------------------------------+

   The supported specification options are subject to the value range of the **Specification** parameter on the page for creating a VPN gateway on the VPN console.

   .. _en-us_topic_0000001854089185__en-us_topic_0000001543354004_table72054:

   .. table:: **Table 4** VpnGatewayAvailabilityZones

      +-----------+-----------------+--------------------------------------------------------------------------------+
      | Parameter | Type            | Description                                                                    |
      +===========+=================+================================================================================+
      | vpc       | Array of String | Specifies the list of AZs for VPN gateways associated with VPCs.               |
      +-----------+-----------------+--------------------------------------------------------------------------------+
      | er        | Array of String | Specifies the list of AZs for VPN gateways associated with enterprise routers. |
      +-----------+-----------------+--------------------------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "availability_zones": {
              "basic": {
                  "vpc": ["eu-de-01"],
                  "er": []
              },
              "professional1": {
                  "vpc": ["eu-de-01", "eu-de-02"],
                  "er": ["eu-de-01"]
                  "er": ["az1"]
              },
              "professional2": {
                  "vpc": ["eu-de-01", "eu-de-02"],
                  "er": ["eu-de-01"]
                  "er": ["az1"]
              },
              "Professional1-NonFixedIP": {
                  "vpc": [],
                  "er": []
              },
              "Professional2-NonFixedIP": {
                  "vpc": [],
                  "er": []
              },
              "gm": {
                  "vpc": [],
                  "er": []
              }
          },
          "request_id": "b60309ab-812c-4269-9de4-fb9a65e6db16"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
