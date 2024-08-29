:original_name: vpn_api_1046.html

.. _vpn_api_1046:

Deleting an IKE Policy
======================

**Function**
------------

This interface is used to delete an IKE policy.

URI
---

DELETE /v2.0/vpn/ikepolicies/{ikepolicy_id}

.. table:: **Table 1** Parameter description

   ============ ====== ========= ============================
   Parameter    Type   Mandatory Description
   ============ ====== ========= ============================
   ikepolicy_id String Yes       Specifies the IKE policy ID.
   ============ ====== ========= ============================

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

      DELETE /v2.0/vpn/ikepolicies/{ikepolicy_id}

-  Example Response

   None

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
