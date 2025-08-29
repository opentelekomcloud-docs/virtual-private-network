:original_name: vpn_api_0066.html

.. _vpn_api_0066:

Querying Project Tags
=====================

Function
--------

This API is used to query all tags of a specified resource type in a specified project of a tenant.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

GET /v5/{project_id}/{resource_type}/tags

.. table:: **Table 1** Parameter description

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                                                                           |
   +=================+=================+=================+=======================================================================================================================================+
   | project_id      | String          | Yes             | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | resource_type   | String          | Yes             | -  Specifies the resource type.                                                                                                       |
   |                 |                 |                 |                                                                                                                                       |
   |                 |                 |                 | -  Value range:                                                                                                                       |
   |                 |                 |                 |                                                                                                                                       |
   |                 |                 |                 |    **vpn-gateway**: S2C VPN gateway                                                                                                   |
   |                 |                 |                 |                                                                                                                                       |
   |                 |                 |                 |    **customer-gateway**: customer gateway                                                                                             |
   |                 |                 |                 |                                                                                                                                       |
   |                 |                 |                 |    **vpn-connection**: VPN connection                                                                                                 |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   None

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v5/{project_id}/{resource_type}/tags

Response
--------

-  Response parameters

   Returned status code 200: successful query

   .. table:: **Table 2** Parameters in the response body

      +-----------+---------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Parameter | Type                                                                                                          | Description                          |
      +===========+===============================================================================================================+======================================+
      | tags      | Array of :ref:`ResourceTag <en-us_topic_0000001807530316__en-us_topic_0000001806475629_table1877710>` objects | Specifies the list of resource tags. |
      +-----------+---------------------------------------------------------------------------------------------------------------+--------------------------------------+

   .. _en-us_topic_0000001807530316__en-us_topic_0000001806475629_table1877710:

   .. table:: **Table 3** ResourceTag

      ========= =============== ======================
      Parameter Type            Description
      ========= =============== ======================
      key       String          Indicates a tag key.
      values    Array of String Indicates a tag value.
      ========= =============== ======================

-  Example response

   .. code-block::

      {
          "tags":[
              {
                  "key":"key1",
                  "values":["value1"]
              }
          ]
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
