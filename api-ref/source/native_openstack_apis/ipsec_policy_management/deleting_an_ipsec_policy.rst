:original_name: en_topic_0093011508.html

.. _en_topic_0093011508:

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

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
