:original_name: vpn_api_0042.html

.. _vpn_api_0042:

Example 3: Creating a VPN Connection
====================================

Scenario
--------

This section describes how to create a VPN connection by calling APIs.

Prerequisites
-------------

-  You have created a VPN gateway. For details, see :ref:`Creating a VPN Gateway <en-us_topic_0000001854169133>`.

-  You have created a customer gateway. For details, see :ref:`Creating a Customer Gateway <en-us_topic_0000001807530292>`.

-  You have obtained a user token if you need to use token authentication. In addition, you need to add **X-Auth-Token** to the request header when calling an API. For details about token authentication, see "Authentication" in the *Virtual Private Cloud API Reference*.

Data Preparation
----------------

.. table:: **Table 1** Key parameters in the request for creating a VPN connection

   +--------------+-----------------------------------------+--------------------------------------+
   | Parameter    | Description                             | Example Value                        |
   +==============+=========================================+======================================+
   | vgw_id       | Specifies a VPN gateway ID.             | b32d91a4-demo-a8df-va86-e907174eb11d |
   +--------------+-----------------------------------------+--------------------------------------+
   | vgw_ip       | Specifies an EIP ID of the VPN gateway. | 0c464dad-demo-a8df-va86-c22bb0eb0bde |
   +--------------+-----------------------------------------+--------------------------------------+
   | cgw_id       | Specifies a customer gateway ID.        | 5247ae10-demo-a8df-va86-dd36659a7f5d |
   +--------------+-----------------------------------------+--------------------------------------+
   | peer_subnets | Specifies a customer subnet.            | 192.168.44.0/24                      |
   +--------------+-----------------------------------------+--------------------------------------+
   | psk          | Specifies a pre-shared key.             | abcd***\*                            |
   +--------------+-----------------------------------------+--------------------------------------+

Procedure
---------

#. Create a VPN connection in static routing mode for a VPN gateway associated with a VPC.

   a. Send **POST https://{endpoint}/v5/{project_id}/vpn-connection**.

   b. Add **X-Auth-Token** to the request header.

   c. Specify the following parameters in the request body:

      .. code-block::

         {
             "vpn_connection": {
                 "vgw_id": "b32d91a4-demo-a8df-va86-e907174eb11d",
                 "vgw_ip": "0c464dad-demo-a8df-va86-c22bb0eb0bde",
                 "cgw_id": "5247ae10-demo-a8df-va86-dd36659a7f5d",
                 "peer_subnets": [
                     "192.168.44.0/24"
                 ],
                 "psk": "abcd****"
             }
         }

   d. Check the response.

      -  The request is successful if the following response is displayed. In the response, **id** indicates a VPN connection ID.

         .. code-block::

            {
                "vpn_connection": {
                    "id": "98c5af8a-demo-a8df-va86-ae2280a6f4c3",
                    "name": "vpn-1655",
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
                    "created_at": "2022-11-26T13:41:34.626Z",
                    "updated_at": "2022-11-26T13:41:34.626Z",
                    "enterprise_project_id": "0",
                },
                "request_id": "f74da97d-aa27-4f62-a87c-a33b5706964b"
            }

#. Query details about the VPN connection.

   a. Send **GET https://{endpoint}/v5/{project_id}/vpn-connection/{vpn_connection_id}**.
   b. Add **X-Auth-Token** to the request header.
   c. Check the response.

      -  The request is successful if the following response is displayed. In the response, **id** indicates a VPN connection ID.

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
                    "created_at": "2022-11-26T13:41:34.626Z",
                    "updated_at": "2022-11-26T13:41:34.626Z",
                    "enterprise_project_id": "0",
                },
                "request_id": "104c5608-b68b-462c-af17-ead2fb5ccee4"
            }
