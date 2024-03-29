:original_name: en_topic_0093011499.html

.. _en_topic_0093011499:

Querying Details About a VPN Service
====================================

**Function**
------------

This interface is used to query details about a VPN service.

URI
---

GET /v2.0/vpn/vpnservices/{service_id}

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

:ref:`Table 2 <en_topic_0093011499__table6499254>` describes the response parameters.

.. _en_topic_0093011499__table6499254:

.. table:: **Table 2** Response parameters

   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter      | Type    | Mandatory | Description                                                                                                                                                                             |
   +================+=========+===========+=========================================================================================================================================================================================+
   | status         | String  | Yes       | Specifies whether the VPN service is currently operational. The value can be **ACTIVE**, **DOWN**, **BUILD**, **ERROR**, **PENDING_CREATE**, **PENDING_UPDATE**, or **PENDING_DELETE**. |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | router_id      | String  | Yes       | Specifies the router ID.                                                                                                                                                                |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name           | String  | No        | Specifies the VPN service name.                                                                                                                                                         |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | external_v6_ip | String  | Yes       | Specifies the IPv6 address of the VPN service external gateway.                                                                                                                         |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up | Boolean | No        | Specifies the administrative status. The value can be **true** or **false**.                                                                                                            |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | subnet_id      | String  | No        | Specifies the subnet ID.                                                                                                                                                                |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id      | String  | No        | Specifies the project ID.                                                                                                                                                               |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | external_v4_ip | String  | Yes       | Specifies the IPv4 address of the VPN service external gateway.                                                                                                                         |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | id             | String  | Yes       | Specifies the VPN service ID.                                                                                                                                                           |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description    | String  | No        | Provides supplementary information about the VPN service.                                                                                                                               |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | vpnservice     | Object  | Yes       | Specifies the VPN service object.                                                                                                                                                       |
   +----------------+---------+-----------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      GET /v2.0/vpn/vpnservices/{service_id}

-  Example Response

   .. code-block::

      {
          "vpnservice": {
              "router_id": "66e3b16c-8ce5-40fb-bb49-ab6d8dc3f2aa",
              "status": "PENDING_CREATE",
              "name": "myservice",
              "external_v6_ip": "2001:db8::1",
              "admin_state_up": true,
              "subnet_id": null,
              "project_id": "10039663455a446d8ba2cbb058b0f578",
              "tenant_id": "10039663455a446d8ba2cbb058b0f578",
              "external_v4_ip": "172.32.1.11",
              "id": "5c561d9d-eaea-45f6-ae3e-08d1a7080828",
              "description": "",
          }
      }

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
