:original_name: vpn_api_1028.html

.. _vpn_api_1028:

Deleting an IPsec VPN Connection
================================

**Function**
------------

This interface is used to delete an IPsec VPN connection.

URI
---

DELETE /v2.0/vpn/ipsec-site-connections/{connection_id}

.. table:: **Table 1** Parameter description

   ============= ====== ========= ======================================
   Parameter     Type   Mandatory Description
   ============= ====== ========= ======================================
   connection_id String Yes       Specifies the IPsec VPN connection ID.
   ============= ====== ========= ======================================

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

      DELETE /v2.0/vpn/ipsec-site-connections/{connection_id}

-  Example Response

   None

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
