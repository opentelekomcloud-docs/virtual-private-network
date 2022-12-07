:original_name: en_topic_0093011488.html

.. _en_topic_0093011488:

Deleting a VPN Resource Tag
===========================

**Function**
------------

This interface is used to delete a VPN resource tag.

URI
---

DELETE /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags/{key}

.. note::

   In the URI, **project_id** indicates the project ID, **resource_id** indicates the target resource ID, and **key** indicates the tag key to be deleted.

Request Message
---------------

None

Response Message
----------------

None

Example
-------

-  Example Request

   .. code-block:: text

      DELETE /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags/{key}

-  Example Response

   None

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
