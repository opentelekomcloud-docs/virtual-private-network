:original_name: en_topic_0093011492.html

.. _en_topic_0093011492:

Creating an IPsec VPN Connection
================================

**Function**
------------

This interface is used to create an IPsec VPN connection.

URI
---

POST /v2.0/vpn/ipsec-site-connections

Request Message
---------------

:ref:`Table 1 <en_topic_0093011492__table64761989>` lists the request parameters for creating an IPsec site connection.

.. _en_topic_0093011492__table64761989:

.. table:: **Table 1** Request parameters

   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | Parameter         | Type         | Mandatory | Description                                                                                                 |
   +===================+==============+===========+=============================================================================================================+
   | dpd               | Object       | No        | Specifies the DPD protocol control.                                                                         |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | local_id          | String       | No        | Specifies the ID of the external gateway address of a virtual router.                                       |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | psk               | String       | Yes       | Specifies the pre-shared key.                                                                               |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | initiator         | String       | No        | Specifies whether this VPN can only respond to connections or both respond to and initiate connections.     |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | ipsecpolicy_id    | String       | Yes       | Specifies the IPsec policy ID.                                                                              |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | admin_state_up    | Boolean      | No        | Specifies the administrative status. The value can be **true** or **false**.                                |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | mtu               | Integer      | No        | Specifies the maximum transmission unit to address fragmentation.                                           |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | peer_ep_group_id  | String       | Yes       | Specifies the endpoint group ID (tenant CIDR blocks).                                                       |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | ikepolicy_id      | String       | Yes       | Specifies the IKE policy ID.                                                                                |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | vpnservice_id     | String       | Yes       | Specifies the VPN service ID.                                                                               |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | local_ep_group_id | String       | Yes       | Specifies the endpoint group ID (VPC subnets).                                                              |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | peer_address      | String       | Yes       | Specifies the remote gateway address.                                                                       |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | peer_id           | String       | Yes       | Specifies the remote gateway ID.                                                                            |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | name              | String       | No        | Specifies the IPsec VPN connection name.                                                                    |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | description       | String       | No        | Provides supplementary information about the IPsec VPN connection.                                          |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | auth_mode         | String       | No        | Specifies the authentication mode. The default value is **psk**.                                            |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | peer_cidrs        | List<String> | No        | (Deprecated) Specifies the tenant's CIDR blocks. The value is in the form of *<net_address > / < prefix >*. |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+
   | tenant_id         | String       | No        | Specifies the project ID.                                                                                   |
   +-------------------+--------------+-----------+-------------------------------------------------------------------------------------------------------------+

.. note::

   #. The **project_id**, **peer_id**, **dpd**, and **local_id** parameters are not supported.
   #. The value of **tenant_id** can contain a maximum of 255 characters.
   #. The value of **name** can contain 1 to 64 characters.
   #. The value of **description** can contain a maximum of 255 characters. This parameter has been used by internal components, and you are not allowed to configure the parameter.
   #. The value of **peer_address** can contain a maximum of 250 characters.
   #. The value of **peer_id** can contain a maximum of 250 characters and is unconfigurable.
   #. The **route_mode** parameter cannot be configured. The default value is **static**.
   #. The value of **mtu** can only be **1500**.
   #. The value of **initiator** can only be **bi-directional**.
   #. The value of **auth_mode** can only be **psk**.
   #. The value of **admin_state_up** can only be **true**.
   #. A PSK can contain 6 to 128 characters. Spaces and question marks (?) are not allowed in a PSK. The PSK cannot contain only asterisks (*).
   #. To enable two IPsec connections to work in active/standby mode, the **local_ep_group_id** and **peer_ep_group_id** parameters of the active and standby connections must be set to the same value. If the parameter values are different and the **local_ep_group** and **peer_ep_group** values are different, the connection cannot work in active/standby mode.

Response Message
----------------

:ref:`Table 2 <en_topic_0093011492__table60218927>` describes the response parameters.

.. _en_topic_0093011492__table60218927:

.. table:: **Table 2** Response parameters

   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | Parameter         | Type    | Description                                                                                                                                                            |
   +===================+=========+========================================================================================================================================================================+
   | interval          | Integer | Specifies the DPD interval in seconds. The default value is **30**.                                                                                                    |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | dpd               | Object  | Specifies the DPD protocol control.                                                                                                                                    |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | psk               | String  | Specifies the pre-shared key.                                                                                                                                          |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | initiator         | String  | Specifies whether this VPN can only respond to connections or both respond to and initiate connections.                                                                |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ipsecpolicy_id    | String  | Specifies the IPsec policy ID.                                                                                                                                         |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | admin_state_up    | Boolean | Specifies the administrative status. The value can be **true** or **false**.                                                                                           |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | mtu               | Integer | Specifies the maximum transmission unit to address fragmentation.                                                                                                      |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | peer_ep_group_id  | String  | Specifies the endpoint group ID (tenant CIDR blocks).                                                                                                                  |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | ikepolicy_id      | String  | Specifies the IKE policy ID.                                                                                                                                           |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | vpnservice_id     | String  | Specifies the VPN service ID.                                                                                                                                          |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | local_ep_group_id | String  | Specifies the endpoint group ID (VPC subnets).                                                                                                                         |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | peer_address      | String  | Specifies the remote gateway address.                                                                                                                                  |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | peer_id           | String  | Specifies the remote gateway ID.                                                                                                                                       |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | name              | String  | Specifies the IPsec VPN connection name.                                                                                                                               |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | description       | String  | Provides supplementary information about the IPsec VPN connection.                                                                                                     |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | auth_mode         | String  | Specifies the authentication mode. The default value is **psk**.                                                                                                       |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | id                | String  | Specifies the IPsec VPN connection ID.                                                                                                                                 |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | route_mode        | String  | Specifies the route advertising mode. The default value is **static**.                                                                                                 |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | status            | String  | Specifies the IPsec VPN connection status. The value can be **ACTIVE**, **DOWN**, **BUILD**, **ERROR**, **PENDING_CREATE**, **PENDING_UPDATE**, or **PENDING_DELETE**. |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | peer_cidrs        | List    | (Deprecated) Specifies the tenant's CIDR blocks. The value is in the form of *<net_address > / < prefix >*.                                                            |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | tenant_id         | String  | Specifies the project ID.                                                                                                                                              |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | timeout           | Integer | Specifies the DPD timeout. The default value is 120 seconds.                                                                                                           |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | action            | String  | Specifies the DPD action. The value can be **clear**, **hold**, **restart**, **disabled**, or **restart-by-peer**. The default value is **hold**.                      |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+
   | created_at        | String  | Specifies the time when the IPsec connection was created.                                                                                                              |
   +-------------------+---------+------------------------------------------------------------------------------------------------------------------------------------------------------------------------+

Example
-------

-  Example Request

   .. code-block:: text

      POST /v2.0/vpn/ipsec-site-connections
      {
        "ipsec_site_connection" : {
          "psk" : "secret",
          "initiator" : "bi-directional",
          "ipsecpolicy_id" : "e6e23d0c-9519-4d52-8ea4-5b1f96d857b1",
          "admin_state_up" : true,
          "mtu" : 1500,
          "peer_ep_group_id" : "9ad5a7e0-6dac-41b4-b20d-a7b8645fddf1",
          "ikepolicy_id" : "9b00d6b0-6c93-4ca5-9747-b8ade7bb514f",
          "vpnservice_id" : "5c561d9d-eaea-45f6-ae3e-08d1a7080828",
          "local_ep_group_id" : "3e1815dd-e212-43d0-8f13-b494fa553e68",
          "peer_address" : "172.24.4.233",
          "peer_id" : "172.24.4.233",
          "name" : "vpnconnection1"
        }
      }

-  Example Response

   .. code-block::

      {
        "ipsec_site_connection" : {
          "status" : "PENDING_CREATE",
          "psk" : "secret",
          "initiator" : "bi-directional",
          "name" : "vpnconnection1",
          "admin_state_up" : true,
          "tenant_id" : "10039663455a446d8ba2cbb058b0f578",
          "auth_mode" : "psk",
          "peer_cidrs" : [ ],
          "mtu" : 1500,
          "peer_ep_group_id" : "9ad5a7e0-6dac-41b4-b20d-a7b8645fddf1",
          "ikepolicy_id" : "9b00d6b0-6c93-4ca5-9747-b8ade7bb514f",
          "vpnservice_id" : "5c561d9d-eaea-45f6-ae3e-08d1a7080828",
          "dpd" : {
            "action" : "hold",
            "interval" : 30,
            "timeout" : 120
          },
          "route_mode" : "static",
          "vpnservice_id": "4754261f-f8c5-4799-a365-78b2e682e38a",
          "ipsecpolicy_id" : "e6e23d0c-9519-4d52-8ea4-5b1f96d857b1",
          "local_ep_group_id" : "3e1815dd-e212-43d0-8f13-b494fa553e68",
          "peer_address" : "172.24.4.233",
          "created_at": "2018-11-03 14:24:33.749714",
          "peer_id" : "172.24.4.233",
          "id" : "851f280f-5639-4ea3-81aa-e298525ab74b",
          "description" : ""
        }
      }

Returned Values
---------------

For details, see section :ref:`Common Returned Values <en_topic_0093011522>`.
