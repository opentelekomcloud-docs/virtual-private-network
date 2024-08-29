:original_name: vpn_api_1034.html

.. _vpn_api_1034:

Deleting a VPN Service
======================

**Function**
------------

This interface is used to delete a VPN service.

.. note::

   This interface cannot be used to delete a VPN service in the active-active VPN scenarios.

URI
---

DELETE /v2.0/vpn/vpnservices/{service_id}

.. table:: **Table 1** Parameter description

   ========== ====== ========= =============================
   Parameter  Type   Mandatory Description
   ========== ====== ========= =============================
   service_id String Yes       Specifies the VPN service ID.
   ========== ====== ========= =============================

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

   DELETE v2.0/vpn/vpnservices/{service_id}

-  Example Response

   None

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
