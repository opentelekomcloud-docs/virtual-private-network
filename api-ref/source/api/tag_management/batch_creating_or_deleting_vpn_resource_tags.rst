:original_name: en_topic_0093011485.html

.. _en_topic_0093011485:

Batch Creating or Deleting VPN Resource Tags
============================================

**Function**
------------

This interface is used to add multiple tags to or delete multiple tags from a VPN resource instance at a time.

This API is idempotent.

If there are duplicate keys in the request body when you add tags, an error is reported.

During tag creation, duplicate keys are not allowed. If a key exists in the database, its value will be overwritten.

During tag deletion, if some tags do not exist, the operation is considered to be successful by default. The character set of the tags will not be checked. When you delete tags, the tag structure cannot be missing, and the key cannot be left blank or be an empty string.

URI
---

POST /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags/action

.. note::

   In the URI, **project_id** indicates the project ID, and **resource_id** indicates the target resource ID.

Request Parameter
-----------------

+-----------+--------------------+-----------+--------------------------------------------------------------------------------+
| Parameter | Type               | Mandatory | Description                                                                    |
+===========+====================+===========+================================================================================+
| tags      | List<resource_tag> | Yes       | Specifies the tag list. A tag list can contain a maximum of 10 keys.           |
+-----------+--------------------+-----------+--------------------------------------------------------------------------------+
| action    | String             | Yes       | Specifies the operation to perform. The value can be **create** or **delete**. |
+-----------+--------------------+-----------+--------------------------------------------------------------------------------+

Description of field **resource_tag**

+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------+
| Name            | Type            | Mandatory                                                                                                             | Description                                                         |
+=================+=================+=======================================================================================================================+=====================================================================+
| key             | String          | Yes                                                                                                                   | Specifies the tag key.                                              |
|                 |                 |                                                                                                                       |                                                                     |
|                 |                 |                                                                                                                       | The parameter constraints are as follows:                           |
|                 |                 |                                                                                                                       |                                                                     |
|                 |                 |                                                                                                                       | -  Must be unique for a resource.                                   |
|                 |                 |                                                                                                                       | -  Cannot be left blank.                                            |
|                 |                 |                                                                                                                       | -  Can contain a maximum of 36 characters.                          |
|                 |                 |                                                                                                                       | -  Can contain only the following character types:                  |
|                 |                 |                                                                                                                       |                                                                     |
|                 |                 |                                                                                                                       |    -  Uppercase letters                                             |
|                 |                 |                                                                                                                       |    -  Lowercase letters                                             |
|                 |                 |                                                                                                                       |    -  Digits                                                        |
|                 |                 |                                                                                                                       |    -  Special characters, including hyphens (-) and underscores (_) |
+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------+
| value           | String          | (This parameter is mandatory when **action** is set to **create** and optional when **action** is set to **delete**.) | Specifies the tag value list.                                       |
|                 |                 |                                                                                                                       |                                                                     |
|                 |                 |                                                                                                                       | The parameter constraints are as follows:                           |
|                 |                 |                                                                                                                       |                                                                     |
|                 |                 |                                                                                                                       | -  Can contain a maximum of 43 characters.                          |
|                 |                 |                                                                                                                       | -  Can contain only the following character types:                  |
|                 |                 |                                                                                                                       |                                                                     |
|                 |                 |                                                                                                                       |    -  Uppercase letters                                             |
|                 |                 |                                                                                                                       |    -  Lowercase letters                                             |
|                 |                 |                                                                                                                       |    -  Digits                                                        |
|                 |                 |                                                                                                                       |    -  Special characters, including hyphens (-) and underscores (_) |
+-----------------+-----------------+-----------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------+

Response Parameter
------------------

None

Example
-------

-  Example Request

   .. code-block:: text

      POST /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags/action

Request Body
------------

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

-  Example Response

   None

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
