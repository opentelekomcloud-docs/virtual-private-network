:original_name: vpn_api_1052.html

.. _vpn_api_1052:

Deleting a VPN Endpoint Group
=============================

**Function**
------------

This interface is used to delete a VPN endpoint group.

URI
---

DELETE /v2.0/vpn/endpoint-groups/{endpoint_group_id}

.. table:: **Table 1** Parameter description

   ================= ====== ========= ====================================
   Parameter         Type   Mandatory Description
   ================= ====== ========= ====================================
   endpoint_group_id String Yes       Specifies the VPN endpoint group ID.
   ================= ====== ========= ====================================

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

   DELETE /v2.0/vpn/endpoint-groups/{endpoint_group_id}

-  Example Response

   None

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
