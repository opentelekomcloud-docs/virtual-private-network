:original_name: vpn_api_0038.html

.. _vpn_api_0038:

Querying Quotas
===============

Function
--------

This API is used to query VPN resource quotas of a tenant, including VPN gateways, customer gateways, and VPN connections.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

GET /v5/{project_id}/vpn/quotas

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

      GET https://{Endpoint}/v5/{project_id}/vpn/quotas

Response
--------

-  Response parameters

   Returned status code 200: successful query

   .. table:: **Table 2** Parameters in the response body

      +------------+----------------------------------------------------------------------------------------------+------------------------------+
      | Parameter  | Type                                                                                         | Description                  |
      +============+==============================================================================================+==============================+
      | quotas     | :ref:`Quotas <en-us_topic_0000001807370484__en-us_topic_0000001543513468_table72132>` object | Specifies the quotas object. |
      +------------+----------------------------------------------------------------------------------------------+------------------------------+
      | request_id | String                                                                                       | Specifies a request ID.      |
      +------------+----------------------------------------------------------------------------------------------+------------------------------+

   .. _en-us_topic_0000001807370484__en-us_topic_0000001543513468_table72132:

   .. table:: **Table 3** Quotas

      +-----------+-------------------------------------------------------------------------------------------------------------------+---------------------------------+
      | Parameter | Type                                                                                                              | Description                     |
      +===========+===================================================================================================================+=================================+
      | resources | Array of :ref:`QuotaInfo <en-us_topic_0000001807370484__en-us_topic_0000001543513468_table1398102318478>` objects | Specifies the resources object. |
      +-----------+-------------------------------------------------------------------------------------------------------------------+---------------------------------+

   .. _en-us_topic_0000001807370484__en-us_topic_0000001543513468_table1398102318478:

   .. table:: **Table 4** QuotaInfo

      +-----------------------+-----------------------+-------------------------------------------------------------+
      | Parameter             | Type                  | Description                                                 |
      +=======================+=======================+=============================================================+
      | type                  | String                | -  Specifies a resource type.                               |
      |                       |                       | -  Value range:                                             |
      |                       |                       |                                                             |
      |                       |                       |    -  **customer_gateway**: customer gateway                |
      |                       |                       |    -  **vpn_connection**: Enterprise Edition VPN connection |
      |                       |                       |    -  **vpn_gateway**: Enterprise Edition VPN gateway       |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | quota                 | Integer               | Specifies the quota upper limit.                            |
      +-----------------------+-----------------------+-------------------------------------------------------------+
      | used                  | Integer               | Specifies the number of resources in use.                   |
      +-----------------------+-----------------------+-------------------------------------------------------------+

-  Example response

   .. code-block::

      {
          "quotas": {
              "resources": [
                  {
                      "type": "customer_gateway",
                      "quota": 100,
                      "used": 13
                  },
                  {
                      "type": "vpn_connection",
                      "quota": 5000,
                      "used": 306
                  },
                  {
                      "type": "vpn_gateway",
                      "quota": 50,
                      "used": 23
                  }
              ]
          },
          "request_id": "9aeb7f73-e1b6-42eb-96ad-b68aef8186e3"
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
