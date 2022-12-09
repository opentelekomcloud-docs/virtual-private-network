:original_name: en_topic_0093011487.html

.. _en_topic_0093011487:

Querying VPN Resource Tags
==========================

**Function**
------------

This interface is used to query tags of a specified VPN resource.

URI
---

GET /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags

.. note::

   In the URI, **project_id** indicates the project ID, and **resource_id** indicates the target resource ID.

Request Message
---------------

None

Response Message
----------------

:ref:`Table 1 <en_topic_0093011487__en-us_topic_0103470567_table1135702419184>` describes the response parameters.

.. _en_topic_0093011487__en-us_topic_0103470567_table1135702419184:

.. table:: **Table 1** Response parameter

   ========= ================== =======================
   Parameter Type               Description
   ========= ================== =======================
   tags      List<resource_tag> Specifies the tag list.
   ========= ================== =======================

Description of field **resource_tag**

+-----------------------+-----------------------+---------------------------------------------------------------------+
| Name                  | Type                  | Description                                                         |
+=======================+=======================+=====================================================================+
| key                   | String                | Specifies the tag key.                                              |
|                       |                       |                                                                     |
|                       |                       | The parameter constraints are as follows:                           |
|                       |                       |                                                                     |
|                       |                       | -  Must be unique for a resource.                                   |
|                       |                       | -  Cannot be left blank.                                            |
|                       |                       | -  Can contain a maximum of 36 characters.                          |
|                       |                       | -  Can contain only the following character types:                  |
|                       |                       |                                                                     |
|                       |                       |    -  Uppercase letters                                             |
|                       |                       |    -  Lowercase letters                                             |
|                       |                       |    -  Digits                                                        |
|                       |                       |    -  Special characters, including hyphens (-) and underscores (_) |
+-----------------------+-----------------------+---------------------------------------------------------------------+
| value                 | String                | Specifies the tag value.                                            |
|                       |                       |                                                                     |
|                       |                       | The parameter constraints are as follows:                           |
|                       |                       |                                                                     |
|                       |                       | -  Can contain a maximum of 43 characters.                          |
|                       |                       | -  Can contain only the following character types:                  |
|                       |                       |                                                                     |
|                       |                       |    -  Uppercase letters                                             |
|                       |                       |    -  Lowercase letters                                             |
|                       |                       |    -  Digits                                                        |
|                       |                       |    -  Special characters, including hyphens (-) and underscores (_) |
+-----------------------+-----------------------+---------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      GET /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags

-  Example Response

   .. code-block::

      {
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

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
