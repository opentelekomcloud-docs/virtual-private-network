:original_name: en_topic_0093011501.html

.. _en_topic_0093011501:

Updating a VPN Service
======================

**Function**
------------

This interface is used to update a VPN service.

URI
---

PUT /v2.0/vpn/vpnservices/{service_id}

.. table:: **Table 1** Parameter description

   ========== ====== ========= =============================
   Parameter  Type   Mandatory Description
   ========== ====== ========= =============================
   service_id String Yes       Specifies the VPN service ID.
   ========== ====== ========= =============================

Request Message
---------------

:ref:`Table 2 <en_topic_0093011501__table24429894>` describes the request parameters.

.. _en_topic_0093011501__table24429894:

.. table:: **Table 2** Request parameters

   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | Parameter      | Type    | Mandatory | Description                                                                  |
   +================+=========+===========+==============================================================================+
   | description    | String  | No        | Provides supplementary information about the VPN service.                    |
   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | name           | String  | No        | Specifies the VPN service name.                                              |
   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | admin_state_up | Boolean | No        | Specifies the administrative status. The value can be **true** or **false**. |
   +----------------+---------+-----------+------------------------------------------------------------------------------+
   | vpnservice     | Object  | Yes       | Specifies the VPN service object.                                            |
   +----------------+---------+-----------+------------------------------------------------------------------------------+

.. note::

   #. The **project_id** parameter is not supported.
   #. The value of **name** can contain 1 to 64 characters.
   #. The value of **description** can contain a maximum of 255 characters.
   #. The value of **admin_state_up** can only be **true**.
   #. The **subnet_id** parameter is unconfigurable.

Response Message
----------------

:ref:`Table 3 <en_topic_0093011501__table9147936>` describes the response parameters.

.. _en_topic_0093011501__table9147936:

.. table:: **Table 3** Response parameters

   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter      | Type    | Mandatory | Description                                                                                                                               |
   +================+=========+===========+===========================================================================================================================================+
   | id             | String  | Yes       | Specifies the VPN service ID.                                                                                                             |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | router_id      | String  | Yes       | Specifies the router ID.                                                                                                                  |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | status         | String  | Yes       | Specifies the VPN service status. The value can be **ACTIVE**, **DOWN**, **BUILD**, **ERROR**, **PENDING_UPDATE**, or **PENDING_DELETE**. |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | name           | String  | Yes       | Specifies the VPN service name.                                                                                                           |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | external_v6_ip | String  | Yes       | Specifies the IPv6 address of the VPN service external gateway.                                                                           |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up | Boolean | Yes       | Specifies the administrative status. The value can be **true** or **false**.                                                              |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | subnet_id      | String  | No        | Specifies the subnet ID.                                                                                                                  |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id      | String  | Yes       | Specifies the project ID.                                                                                                                 |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | external_v4_ip | String  | Yes       | Specifies the IPv4 address of the VPN service external gateway.                                                                           |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | description    | String  | Yes       | Provides supplementary information about the VPN service.                                                                                 |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+
   | vpnservice     | Object  | Yes       | Specifies the VPN service object.                                                                                                         |
   +----------------+---------+-----------+-------------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      PUT /v2.0/vpn/vpnservices/{service_id}
      {
        "vpnservice" : {
          "description" : "Updated description"
        }
      }

-  Example Response

   .. code-block::

      {
          "vpnservice": {
              "router_id": "881b7b30-4efb-407e-a162-5630a7af3595",
              "status": "ACTIVE",
              "name": "myvpn",
              "admin_state_up": true,
              "subnet_id": null,
              "project_id": "26de9cd6cae94c8cb9f79d660d628e1f",
              "tenant_id": "26de9cd6cae94c8cb9f79d660d628e1f",
              "id": "41bfef97-af4e-4f6b-a5d3-4678859d2485",
              "description": "Updated description",
          }
      }

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
