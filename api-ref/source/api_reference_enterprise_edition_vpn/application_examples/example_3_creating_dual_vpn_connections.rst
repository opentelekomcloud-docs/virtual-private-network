:original_name: vpn_api_0042.html

.. _vpn_api_0042:

Example 3: Creating Dual VPN Connections
========================================

Scenario
--------

This section describes how to create dual VPN connections by calling APIs.

Prerequisites
-------------

-  You have created a VPN gateway. For details, see :ref:`Creating a VPN Gateway <en-us_topic_0000001854169133>`.

-  You have created a customer gateway. For details, see :ref:`Creating a Customer Gateway <en-us_topic_0000001807530292>`.

-  You have obtained a user token if you need to use token authentication. In addition, you need to add **X-Auth-Token** to the request header when calling an API. For details about token authentication, see "Authentication" in the *Virtual Private Cloud API Reference*.

Data Preparation
----------------

.. table:: **Table 1** Key parameters in the request for creating VPN connections

   +--------------+-----------------------------------------------+--------------------------------------+
   | Parameter    | Description                                   | Example Value                        |
   +==============+===============================================+======================================+
   | vgw_id       | Specifies a VPN gateway ID.                   | 8030f6d6-demo-4d20-a7f8-50a7a826e2f8 |
   +--------------+-----------------------------------------------+--------------------------------------+
   | vgw_ip1      | Specifies the ID of EIP 1 of the VPN gateway. | e4d7930f-demo-4cbf-b78a-b004416c7485 |
   +--------------+-----------------------------------------------+--------------------------------------+
   | vgw_ip2      | Specifies the ID of EIP 2 of the VPN gateway. | 1fb97767-demo-4d8b-83bb-6f878f662005 |
   +--------------+-----------------------------------------------+--------------------------------------+
   | cgw_id       | Specifies a customer gateway ID.              | 8916effb-demo-42d8-83d7-4517567d3d26 |
   +--------------+-----------------------------------------------+--------------------------------------+
   | peer_subnets | Specifies a customer subnet.                  | 192.168.44.0/24                      |
   +--------------+-----------------------------------------------+--------------------------------------+
   | psk          | Specifies a pre-shared key.                   | abcd***\*                            |
   +--------------+-----------------------------------------------+--------------------------------------+

Procedure
---------

#. Create VPN connections in static routing mode for a VPN gateway associated with a VPC.

   a. Send **POST https://{endpoint}/v5/{project_id}/vpn-connections/batch-create**.

   b. Add **X-Auth-Token** to the request header.

   c. Specify the following parameters in the request body:

      .. code-block::

         {
             "vpn_connections": [
                 {
                     "vgw_ip": "e4d7930f-demo-4cbf-b78a-b004416c7485",
                     "cgw_id": "8916effb-demo-42d8-83d7-4517567d3d26",
                     "vgw_id": "8030f6d6-demo-4d20-a7f8-50a7a826e2f8",
                     "peer_subnets": [
                         "192.168.44.0/24"
                     ],
                     "psk": "abcd****"
                 },
                 {
                     "vgw_ip": "1fb97767-demo-4d8b-83bb-6f878f662005",
                     "cgw_id": "8916effb-demo-42d8-83d7-4517567d3d26",
                     "vgw_id": "8030f6d6-demo-4d20-a7f8-50a7a826e2f8",
                     "peer_subnets": [
                         "192.168.44.0/24"
                     ],
                     "psk": "abcd****"
                 }
             ]
         }

   d. Check the response.

      -  The request is successful if the following response is displayed. In the response, there are two **id** fields, each indicating a VPN connection ID.

         .. code-block::

            {
                "vpn_connections": [
                    {
                        "id": "18be2aa1-demo-410f-832e-4d8ba13b4c5d",
                        "name": "vpn-22b6",
                        "vgw_id": "8030f6d6-demo-4d20-a7f8-50a7a826e2f8",
                        "vgw_ip": "e4d7930f-demo-4cbf-b78a-b004416c7485",
                        "style": "STATIC",
                        "cgw_id": "8916effb-demo-42d8-83d7-4517567d3d26",
                        "peer_subnets": [
                            "192.168.44.0/24"
                        ],
                        "tunnel_local_address": "169.254.135.49/30",
                        "tunnel_peer_address": "169.254.135.50/30",
                        "enable_nqa": false,
                        "policy_rules": [],
                        "ikepolicy": {
                            "ike_version": "v2",
                            "authentication_algorithm": "sha2-256",
                            "encryption_algorithm": "aes-128",
                            "dh_group": "group15",
                            "authentication_method": "pre-share",
                            "lifetime_seconds": 86400,
                            "local_id_type": "ip",
                            "local_id": "10.***.***.128",
                            "peer_id_type": "ip",
                            "peer_id": "188.***.***.189",
                            "dpd": {
                                "interval": 30,
                                "timeout": 15,
                                "msg": "seq-hash-notify"
                            }
                        },
                        "ipsecpolicy": {
                            "authentication_algorithm": "sha2-256",
                            "encryption_algorithm": "aes-128",
                            "pfs": "group15",
                            "transform_protocol": "esp",
                            "lifetime_seconds": 3600,
                            "encapsulation_mode": "tunnel"
                        },
                        "created_at": "2025-03-17T12:25:21.369Z",
                        "updated_at": "2025-03-17T12:25:21.369Z",
                        "enterprise_project_id": "0",
                        "ha_role": "master",
                        "tags": [],
                    },
                    {
                        "id": "c7e617bd-877f-demo-8af0-44b5f8598116",
                        "name": "vpn-e41c",
                        "vgw_id": "8030f6d6-demo-4d20-a7f8-50a7a826e2f8",
                        "vgw_ip": "1fb97767-demo-4d8b-83bb-6f878f662005",
                        "style": "STATIC",
                        "cgw_id": "8916effb-demo-42d8-83d7-4517567d3d26",
                        "peer_subnets": [
                            "192.168.44.0/24"
                        ],
                        "tunnel_local_address": "169.254.73.253/30",
                        "tunnel_peer_address": "169.254.73.254/30",
                        "enable_nqa": false,
                        "policy_rules": [],
                        "ikepolicy": {
                            "ike_version": "v2",
                            "authentication_algorithm": "sha2-256",
                            "encryption_algorithm": "aes-128",
                            "dh_group": "group15",
                            "authentication_method": "pre-share",
                            "lifetime_seconds": 86400,
                            "local_id_type": "ip",
                            "local_id": "215.***.***.55",
                            "peer_id_type": "ip",
                            "peer_id": "188.***.***.189",
                            "dpd": {
                                "interval": 30,
                                "timeout": 15,
                                "msg": "seq-hash-notify"
                            }
                        },
                        "ipsecpolicy": {
                            "authentication_algorithm": "sha2-256",
                            "encryption_algorithm": "aes-128",
                            "pfs": "group15",
                            "transform_protocol": "esp",
                            "lifetime_seconds": 3600,
                            "encapsulation_mode": "tunnel"
                        },
                        "created_at": "2025-03-17T12:25:21.678Z",
                        "updated_at": "2025-03-17T12:25:21.678Z",
                        "enterprise_project_id": "0",
                        "ha_role": "master",
                        "tags": [],
                    }
                ],
                "request_id": "a923f31456941e12c5fc9a663a6e630e"
            }

#. Query VPN connections.

   a. Send **GET https://{endpoint}/v5/{project_id}/vpn-connection/{vpn_connection_id}**.
   b. Add **X-Auth-Token** to the request header.
   c. Check the response.

      -  The request is successful if the following response is displayed. In the response, there are two **id** fields, each indicating a VPN connection ID.

         .. code-block::

            {
                "vpn_connection": {
                    "id": "98c5af8a-demo-a8df-va86-ae2280a6f4c3",
                    "name": "vpn-1655",
                    "status": "DOWN",
                    "vgw_id": "b32d91a4-demo-a8df-va86-e907174eb11d",
                    "vgw_ip": "0c464dad-demo-a8df-va86-c22bb0eb0bde",
                    "style": "STATIC",
                    "cgw_id": "5247ae10-demo-a8df-va86-dd36659a7f5d",
                    "peer_subnets": ["192.168.44.0/24"],
                    "tunnel_local_address": "169.254.56.225/30",
                    "tunnel_peer_address": "169.254.56.226/30",
                    "enable_nqa": false,
                    "ikepolicy": {
                        "ike_version": "v2",
                        "authentication_algorithm": "sha2-256",
                        "encryption_algorithm": "aes-128",
                        "dh_group": "group15",
                        "authentication_method": "pre-share",
                        "lifetime_seconds": 86400,
                        "local_id_type": "ip",
                        "local_id": "10.***.***.134",
                        "peer_id_type": "ip",
                        "peer_id": "88.***.***.164",
                        "dpd": {
                            "timeout": 15,
                            "interval": 30,
                            "msg": "seq-hash-notify"
                        }
                    },
                    "ipsecpolicy": {
                        "authentication_algorithm": "sha2-256",
                        "encryption_algorithm": "aes-128",
                        "pfs": "group15",
                        "transform_protocol": "esp",
                        "lifetime_seconds": 3600,
                        "encapsulation_mode": "tunnel"
                    },
                    "created_at": "2025-06-26T13:41:34.626Z",
                    "updated_at": "2025-06-26T13:41:34.626Z",
                    "enterprise_project_id": "0",
                },
                "request_id": "104c5608-b68b-462c-af17-ead2fb5ccee4"
            }


            {
                "vpn_connection": {
                    "id": "18be2aa1-demo-410f-832e-4d8ba13b4c5d",
                    "name": "vpn-22b6",
                    "status": "DOWN",
                    "vgw_id": "8030f6d6-demo-4d20-a7f8-50a7a826e2f8",
                    "vgw_ip": "e4d7930f-demo-4cbf-b78a-b004416c7485",
                    "style": "STATIC",
                    "cgw_id": "8916effb-demo-42d8-83d7-4517567d3d26",
                    "peer_subnets": [
                        "192.168.44.0/24"
                    ],
                    "tunnel_local_address": "169.254.135.49/30",
                    "tunnel_peer_address": "169.254.135.50/30",
                    "enable_nqa": false,
                    "policy_rules": [],
                    "ikepolicy": {
                        "ike_version": "v2",
                        "authentication_algorithm": "sha2-256",
                        "encryption_algorithm": "aes-128",
                        "dh_group": "group15",
                        "authentication_method": "pre-share",
                        "lifetime_seconds": 86400,
                        "local_id_type": "ip",
                        "local_id": "10.***.***.128",
                        "peer_id_type": "ip",
                        "peer_id": "188.***.***.189",
                        "dpd": {
                            "interval": 30,
                            "timeout": 15,
                            "msg": "seq-hash-notify"
                        }
                    },
                    "ipsecpolicy": {
                        "authentication_algorithm": "sha2-256",
                        "encryption_algorithm": "aes-128",
                        "pfs": "group15",
                        "transform_protocol": "esp",
                        "lifetime_seconds": 3600,
                        "encapsulation_mode": "tunnel"
                    },
                    "created_at": "2025-03-17T12:25:21.369Z",
                    "updated_at": "2025-03-17T12:25:21.369Z",
                    "enterprise_project_id": "0",
                    "ha_role": "master",
                    "tags": [],
                    "eip_id": "e4d7930f-7038-4cbf-b78a-b004416c7485",
                    "type": "ROUTE",
                    "route_mode": "STATIC"
                },
                "request_id": "62dc155a7353037f0a1ccc569016a3e9"
            }
