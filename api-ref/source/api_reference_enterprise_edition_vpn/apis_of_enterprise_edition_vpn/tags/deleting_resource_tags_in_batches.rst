:original_name: vpn_api_0064.html

.. _vpn_api_0064:

Deleting Resource Tags in Batches
=================================

Function
--------

This API is used to delete tags from a specified instance in batches.

Calling Method
--------------

For details, see :ref:`Calling APIs <en-us_topic_0000001807530276>`.

URI
---

POST /v5/{project_id}/{resource_type}/{resource_id}/tags/delete

.. table:: **Table 1** Parameter description

   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                                                                           |
   +=================+=================+=================+=======================================================================================================================================+
   | project_id      | String          | Yes             | Specifies a project ID. You can obtain the project ID by referring to :ref:`Obtaining the Project ID <en-us_topic_0000001807530332>`. |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | resource_type   | String          | Yes             | -  Specifies the resource type.                                                                                                       |
   |                 |                 |                 | -  The value can be **vpn-gateway**, **customer-gateway**, or **vpn-connection**.                                                     |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+
   | resource_id     | String          | Yes             | Indicates a resource ID.                                                                                                              |
   +-----------------+-----------------+-----------------+---------------------------------------------------------------------------------------------------------------------------------------+

Request
-------

-  Request parameters

   .. table:: **Table 2** Request parameters

      +-----------------+-------------------------------------------------------------------------------------------------------------+-----------------+-------------------------------------------+
      | Parameter       | Type                                                                                                        | Mandatory       | Description                               |
      +=================+=============================================================================================================+=================+===========================================+
      | tags            | Array of :ref:`ResourceTag <en-us_topic_0000001854169165__en-us_topic_0000001806394645_table92196>` objects | Yes             | -  Specifies a tag list.                  |
      |                 |                                                                                                             |                 | -  A maximum of 20 tags can be specified. |
      +-----------------+-------------------------------------------------------------------------------------------------------------+-----------------+-------------------------------------------+

   .. _en-us_topic_0000001854169165__en-us_topic_0000001806394645_table92196:

   .. table:: **Table 3** ResourceTag

      +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | Parameter       | Type            | Mandatory       | Description                                                                                                                                                                      |
      +=================+=================+=================+==================================================================================================================================================================================+
      | key             | String          | Yes             | -  Specifies a tag key.                                                                                                                                                          |
      |                 |                 |                 | -  The value is a string of 1 to 128 characters that can contain digits, letters, Spanish characters, Portuguese characters, spaces, and special characters (``_ . : = + - @``). |
      +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
      | value           | String          | No              | -  Specifies a tag value.                                                                                                                                                        |
      |                 |                 |                 | -  The value is a string of 0 to 255 characters that can contain digits, letters, Spanish characters, Portuguese characters, spaces, and special characters (``_ . : = + - @``). |
      +-----------------+-----------------+-----------------+----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

-  Example request

   .. code-block:: text

      DELETE https://{Endpoint}/v5/{project_id}/{resource_type}/{resource_id}/tags/delete
      {
          "tags": [{
              "key": "key1",
              "value": "value1"
          }]
      }

Response
--------

-  Response parameters

   Returned status code 204: Tags are successfully deleted.

Status Codes
------------

For details, see :ref:`Status Codes <en-us_topic_0000001807370508>`.
