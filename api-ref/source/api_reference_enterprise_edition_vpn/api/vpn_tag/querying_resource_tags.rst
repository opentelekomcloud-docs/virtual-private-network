:original_name: vpn_api_0065.html

.. _vpn_api_0065:

Querying Resource Tags
======================

Function
--------

This API is used to query tags of a specified instance.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

GET /v5/{project_id}/{resource_type}/{resource_id}/tags

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
   | resource_id     | String          | Yes             | Indicates a resource ID.                                                                                                              |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   None

-  Example request

   .. code-block:: text

      GET https://{Endpoint}/v5/{project_id}/{resource_type}/{resource_id}/tags

Response
--------

-  Response parameters

   Returned status code 200: successful query

   .. table:: **Table 2** Parameters in the response body

      +-----------+---------------------------------------------------------------------------------------------------------------+--------------------------------------+
      | Parameter | Type                                                                                                          | Description                          |
      +===========+===============================================================================================================+======================================+
      | tags      | Array of :ref:`ResourceTag <en-us_topic_0000001854089213__en-us_topic_0000001759396190_table1877710>` objects | Specifies the list of resource tags. |
      +-----------+---------------------------------------------------------------------------------------------------------------+--------------------------------------+

   .. _en-us_topic_0000001854089213__en-us_topic_0000001759396190_table1877710:

   .. table:: **Table 3** ResourceTag

      ========= ====== ======================
      Parameter Type   Description
      ========= ====== ======================
      key       String Specifies a tag key.
      value     String Specifies a tag value.
      ========= ====== ======================

-  Example response

   .. code-block::

      {
          "tags":[
              {
                  "key":"key1",
                  "value":"value1"
              }
          ]
      }

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
