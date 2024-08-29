:original_name: vpn_api_1020.html

.. _vpn_api_1020:

Deleting VPN Tags
=================

Function
--------

This API is used to delete VPN tags.

URI
---

DELETE /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags/{key}

.. note::

   In the URI, **project_id** indicates the project ID, **resource_id** indicates the ID of the target resource, and **key** indicates the tag key to be deleted.

Request
-------

None

Response
--------

None

Example
-------

-  Example request

   .. code-block:: text

      DELETE /v2.0/{project_id}/ipsec-site-connections/{resource_id}/tags/{key}

-  Example response

   None

Returned Values
---------------

For details, see :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
