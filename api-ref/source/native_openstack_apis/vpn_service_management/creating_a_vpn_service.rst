:original_name: en_topic_0093011498.html

.. _en_topic_0093011498:

Creating a VPN Service
======================

**Function**
------------

This interface is used to create a VPN service.

.. note::

   Only one VPN service can be created for each VPC.

URI
---

POST /v2.0/vpn/vpnservices

Request Message
---------------

:ref:`Table 1 <en_topic_0093011498__table35351135>` describes the request parameters.

.. _en_topic_0093011498__table35351135:

.. table:: **Table 1** Request parameters

   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | Parameter      | Type    | Mandatory | Description                                                                  |
   +================+=========+===========+==============================================================================+
   | subnet_id      | String  | No        | Specifies the subnet ID.                                                     |
   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | router_id      | String  | Yes       | Specifies the router ID.                                                     |
   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | name           | String  | No        | Specifies the VPN service name.                                              |
   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | admin_state_up | Boolean | No        | Specifies the administrative status. The value can be **true** or **false**. |
   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | tenant_id      | String  | No        | Specifies the project ID.                                                    |
   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | description    | String  | No        | Provides supplementary information about the VPN service.                    |
   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | vpnservice     | Object  | Yes       | Specifies the VPN service object.                                            |
   +----------------+---------+-----------+------------------------------------------------------------------------------+

.. note::

   #. The **project_id** parameter is not supported.
   #. The value of **tenant_id** can contain a maximum of 255 characters.
   #. The value of **name** can contain 1 to 64 characters.
   #. The value of **description** can contain a maximum of 255 characters.
   #. The value of **router_id** must be the VPC router ID.
   #. The value of **admin_state_up** can only be **true**.
   #. This interface cannot be used to create a VPN service in the active-active VPN scenarios.
   #. Bandwidth limiting is used by default. The recommended bandwidth is 300 Mbit/s. This interface cannot be used to change the bandwidth size.
   #. In standalone mode, only one VPC service can be created for each VPN. In active-active mode, two VPC services can be created for each VPN.

Response Message
----------------

:ref:`Table 2 <en_topic_0093011498__table1362895>` describes the response parameters.

.. _en_topic_0093011498__table1362895:

.. table:: **Table 2** Response parameters

   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter      | Type    | Description                                                                                                                                                                             |
   +================+=========+=========================================================================================================================================================================================+
   | router_id      | String  | Specifies the router ID.                                                                                                                                                                |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status         | String  | Specifies whether the VPN service is currently operational. The value can be **ACTIVE**, **DOWN**, **BUILD**, **ERROR**, **PENDING_CREATE**, **PENDING_UPDATE**, or **PENDING_DELETE**. |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name           | String  | Specifies the VPN service name.                                                                                                                                                         |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | external_v6_ip | String  | Specifies the IPv6 address of the VPN service external gateway.                                                                                                                         |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up | Boolean | Specifies the administrative status. The value can be **true** or **false**.                                                                                                            |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | subnet_id      | String  | Specifies the subnet ID.                                                                                                                                                                |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id      | String  | Specifies the project ID.                                                                                                                                                               |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | external_v4_ip | String  | Specifies the IPv4 address of the VPN service external gateway.                                                                                                                         |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | id             | String  | Specifies the VPN service ID.                                                                                                                                                           |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description    | String  | Provides supplementary information about the VPN service.                                                                                                                               |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | vpnservice     | Object  | Specifies the VPN service object.                                                                                                                                                       |
   +----------------+---------+-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      POST /v2.0/vpn/vpnservices
      {
          "vpnservice": {
              "subnet_id": null,
              "router_id": "66e3b16c-8ce5-40fb-bb49-ab6d8dc3f2aa",
              "name": "myservice",
              "admin_state_up": true
          }
      }

-  Example Response

   .. code-block::

      {
        "vpnservice" : {
          "router_id" : "66e3b16c-8ce5-40fb-bb49-ab6d8dc3f2aa",
          "status" : "PENDING_CREATE",
          "name" : "myservice",
          "external_v6_ip" : "2001:db8::1",
          "admin_state_up" : true,
          "subnet_id" : null,
          "project_id" : "10039663455a446d8ba2cbb058b0f578",
          "tenant_id" : "10039663455a446d8ba2cbb058b0f578",
          "external_v4_ip" : "172.32.1.11",
          "id" : "5c561d9d-eaea-45f6-ae3e-08d1a7080828",
          "description" : ""
        }
      }

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
