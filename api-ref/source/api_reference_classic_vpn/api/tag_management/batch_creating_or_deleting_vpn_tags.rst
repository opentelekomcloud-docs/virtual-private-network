:original_name: vpn_api_1017.html

.. _vpn_api_1017:

Batch Creating or Deleting VPN Tags
===================================

Function
--------

This API is used to batch create or delete VPN tags.

This API is idempotent.

-  If there are duplicate keys in the request body when you add tags, an error is reported.
-  During tag creation, each key must be unique. If the key already exists, the previous value of the key is overwritten.
-  If the tag to be deleted does not exist, the deletion is considered successful by default.
-  During tag deletion, the value range of the tag character set is not verified.
-  When you delete tags, **tags** is mandatory, and **key** cannot be left blank or be an empty string.

URI
---

POST /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags/action

.. note::

   In the URI, **project_id** indicates the project ID, and **resource_id** indicates the ID of the target resource.

Request
-------

:ref:`Table 1 <en-us_topic_0000001854169201__en-us_topic_0000001591616793_en-us_topic_0103470569_table2726185911818>` describes the request parameters.

.. _en-us_topic_0000001854169201__en-us_topic_0000001591616793_en-us_topic_0103470569_table2726185911818:

.. table:: **Table 1** Request parameters

   +-----------------+--------------------+-----------------+-------------------------------------------------+
   | Parameter       | Type               | Mandatory       | Description                                     |
   +=================+====================+=================+=================================================+
   | tags            | List<resource_tag> | Yes             | Specifies the list of tags.                     |
   |                 |                    |                 |                                                 |
   |                 |                    |                 | Up to 10 keys are supported.                    |
   +-----------------+--------------------+-----------------+-------------------------------------------------+
   | action          | String             | Yes             | Specifies the operation identifier.             |
   |                 |                    |                 |                                                 |
   |                 |                    |                 | The identifier can be **create** or **delete**. |
   +-----------------+--------------------+-----------------+-------------------------------------------------+

.. table:: **Table 2** Description of field **resource_tag**

   +-----------------+-----------------+-----------------------------------------------------------------+----------------------------------------------------+
   | Name            | Type            | Mandatory                                                       | Description                                        |
   +=================+=================+=================================================================+====================================================+
   | key             | String          | Yes                                                             | Specifies the tag key.                             |
   |                 |                 |                                                                 |                                                    |
   |                 |                 |                                                                 | The key                                            |
   |                 |                 |                                                                 |                                                    |
   |                 |                 |                                                                 | -  Must be unique for a resource.                  |
   |                 |                 |                                                                 | -  Cannot be left blank.                           |
   |                 |                 |                                                                 | -  Can contain a maximum of 36 characters.         |
   |                 |                 |                                                                 | -  Can contain only the following character types: |
   |                 |                 |                                                                 |                                                    |
   |                 |                 |                                                                 |    -  Uppercase letters                            |
   |                 |                 |                                                                 |    -  Lowercase letters                            |
   |                 |                 |                                                                 |    -  Digits                                       |
   |                 |                 |                                                                 |    -  Hyphens (-) and underscores (_)              |
   +-----------------+-----------------+-----------------------------------------------------------------+----------------------------------------------------+
   | value           | String          | -  **value** is mandatory when **action** is set to **create**. | Specifies the list of tag values.                  |
   |                 |                 | -  **value** is optional when **action** is set to **delete**.  |                                                    |
   |                 |                 |                                                                 | The value                                          |
   |                 |                 |                                                                 |                                                    |
   |                 |                 |                                                                 | -  Can contain a maximum of 43 characters.         |
   |                 |                 |                                                                 | -  Can contain only the following character types: |
   |                 |                 |                                                                 |                                                    |
   |                 |                 |                                                                 |    -  Uppercase letters                            |
   |                 |                 |                                                                 |    -  Lowercase letters                            |
   |                 |                 |                                                                 |    -  Digits                                       |
   |                 |                 |                                                                 |    -  Hyphens (-) and underscores (_)              |
   +-----------------+-----------------+-----------------------------------------------------------------+----------------------------------------------------+

Response
--------

None

Example
-------

-  Example request

   .. code-block:: text

      POST /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags/action

   Request body

   .. code-block::

      {
          "action": "create",
          "tags": [
              {
                  "key": "key1",
                  "value": "value1"
              },
              {
                  "key": "key",
                  "value": "value3"
              }
          ]
      }

   Or

   .. code-block::

      {
          "action": "delete",
          "tags": [
              {
                  "key": "key1",
                  "value": "value1"
              },
              {
                  "key": "key2",
                  "value": "value3"
              }
          ]
      }

-  Example response

   None

Returned Values
---------------

For details, see :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
