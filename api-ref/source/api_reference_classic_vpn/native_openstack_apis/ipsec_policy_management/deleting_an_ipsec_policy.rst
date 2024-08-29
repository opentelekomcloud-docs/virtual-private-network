:original_name: vpn_api_1040.html

.. _vpn_api_1040:

Deleting an IPsec Policy
========================

**Function**
------------

This interface is used to delete an IPsec policy.

URI
---

DELETE /v2.0/vpn/ipsecpolicies/{ipsecpolicy_id}

.. table:: **Table 1** Parameter description

   ============== ====== ========= ==============================
   Parameter      Type   Mandatory Description
   ============== ====== ========= ==============================
   ipsecpolicy_id String Yes       Specifies the IPsec policy ID.
   ============== ====== ========= ==============================

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

   DELETE /v2.0/vpn/ipsecpolicies/{ipsecpolicy_id}

-  Example Response

   None

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
