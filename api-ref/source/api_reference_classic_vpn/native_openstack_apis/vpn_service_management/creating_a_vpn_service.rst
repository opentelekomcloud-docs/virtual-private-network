:original_name: vpn_api_1030.html

.. _vpn_api_1030:

Creating a VPN Service
======================

Function
--------

This API is used to create a VPN service.

.. note::

   Only one VPN service can be created for each VPC.

URI
---

POST /v2.0/vpn/vpnservices

Request
-------

:ref:`Table 1 <en-us_topic_0000001854089261__en-us_topic_0000001541296746_table35351135>` describes the request parameters.

.. _en-us_topic_0000001854089261__en-us_topic_0000001541296746_table35351135:

.. table:: **Table 1** Request parameters

   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------+
   | Parameter       | Type            | Mandatory       | Description                                                                                            |
   +=================+=================+=================+========================================================================================================+
   | subnet_id       | String          | No              | Specifies the subnet ID.                                                                               |
   |                 |                 |                 |                                                                                                        |
   |                 |                 |                 | The subnet here is the VPC subnet. Query the subnet and enter the correct ID.                          |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------+
   | router_id       | String          | Yes             | Specifies the router ID.                                                                               |
   |                 |                 |                 |                                                                                                        |
   |                 |                 |                 | The value of **router_id** must be the VPC router ID.                                                  |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------+
   | name            | String          | No              | Specifies the VPN service name.                                                                        |
   |                 |                 |                 |                                                                                                        |
   |                 |                 |                 | The name can contain 1 to 64 characters.                                                               |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------+
   | admin_state_up  | Boolean         | No              | Specifies the administrative status, which can be **true** or **false**.                               |
   |                 |                 |                 |                                                                                                        |
   |                 |                 |                 | Currently, **admin_state_up** can only be **true**.                                                    |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------+
   | tenant_id       | String          | No              | Specifies the project ID.                                                                              |
   |                 |                 |                 |                                                                                                        |
   |                 |                 |                 | The ID can contain up to 255 characters.                                                               |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------+
   | description     | String          | No              | Provides supplementary information about the VPN service.                                              |
   |                 |                 |                 |                                                                                                        |
   |                 |                 |                 | The description can contain up to 255 characters.                                                      |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------+
   | external_v4_ip  | String          | No              | Specifies the IPv4 address of the VPN service external gateway.                                        |
   |                 |                 |                 |                                                                                                        |
   |                 |                 |                 | The address can contain up to 255 characters.                                                          |
   |                 |                 |                 |                                                                                                        |
   |                 |                 |                 | .. note::                                                                                              |
   |                 |                 |                 |                                                                                                        |
   |                 |                 |                 |    When you configure this parameter, ensure that the tenant meets one of the following conditions:    |
   |                 |                 |                 |                                                                                                        |
   |                 |                 |                 |    -  **role** is **admin**.                                                                           |
   |                 |                 |                 |    -  **role** is **internal_admin**.                                                                  |
   |                 |                 |                 |    -  **role** is **op_service**.                                                                      |
   |                 |                 |                 |    -  **role** is **vpn_adm** and operations can be performed only on resources of the current tenant. |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------+
   | vpnservice      | Object          | Yes             | Specifies the VPN service object.                                                                      |
   +-----------------+-----------------+-----------------+--------------------------------------------------------------------------------------------------------+

.. note::

   -  Parameter **project_id** is not supported.
   -  This API cannot be used to create a VPN service that works in active- standby mode with a Direct Connect connection.
   -  Bandwidth limiting is used by default. The recommended bandwidth is 300 Mbit/s. This API cannot be used to change the bandwidth size.
   -  In the standalone scenario, one VPC corresponds to one VPN service. In the active-active scenario, one VPC corresponds to two VPN services.

Response
--------

:ref:`Table 2 <en-us_topic_0000001854089261__en-us_topic_0000001541296746_table1362895>` describes the response parameters.

.. _en-us_topic_0000001854089261__en-us_topic_0000001541296746_table1362895:

.. table:: **Table 2** Response parameters

   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter             | Type                  | Description                                                                                                                                                                   |
   +=======================+=======================+===============================================================================================================================================================================+
   | router_id             | String                | Specifies the router ID.                                                                                                                                                      |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status                | String                | Specifies whether the VPN service is operational. The value can be **ACTIVE**, **DOWN**, **BUILD**, **ERROR**, **PENDING_CREATE**, **PENDING_UPDATE**, or **PENDING_DELETE**. |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name                  | String                | Specifies the VPN service name.                                                                                                                                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | external_v6_ip        | String                | Specifies the IPv6 address of the VPN service external gateway.                                                                                                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up        | Boolean               | Specifies the administrative status, which can be **true** or **false**.                                                                                                      |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | subnet_id             | String                | Specifies the subnet ID.                                                                                                                                                      |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id             | String                | Specifies the project ID.                                                                                                                                                     |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | external_v4_ip        | String                | Specifies the IPv4 address of the VPN service external gateway.                                                                                                               |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | id                    | String                | Specifies the VPN service ID.                                                                                                                                                 |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description           | String                | Provides supplementary information about the VPN service.                                                                                                                     |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at            | String                | Specifies the time when the VPN service was created.                                                                                                                          |
   |                       |                       |                                                                                                                                                                               |
   |                       |                       | The time is in *YYYY-mm-dd HH:MM:SS.ffffff* format.                                                                                                                           |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | vpnservice            | Object                | Specifies the VPN service object.                                                                                                                                             |
   +-----------------------+-----------------------+-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

-  Example request

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

-  Example response

   .. code-block::

      {
        "vpnservice" : {
          "router_id" : "66e3b16c-8ce5-40fb-bb49-ab6d8dc3f2aa",
          "status" : "PENDING_CREATE",
          "name" : "myservice",
          "external_v6_ip" : "2001:db8::1",
          "admin_state_up" : true,
          "subnet_id" : null,
          "tenant_id" : "10039663455a446d8ba2cbb058b0f578",
          "external_v4_ip" : "172.32.1.11",
          "id" : "5c561d9d-eaea-45f6-ae3e-08d1a7080828",
          "description" : "",
          "prepay_connection_num": 0,
          "resource_speccode": "",
          "order_id": "",
          "product_id": "",
          "created_at": "2020-08-05 12:36:35.921257"
        }
      }

Returned Values
---------------

For details, see :ref:`Common Returned Values <en-us_topic_0000001854089293>`.
