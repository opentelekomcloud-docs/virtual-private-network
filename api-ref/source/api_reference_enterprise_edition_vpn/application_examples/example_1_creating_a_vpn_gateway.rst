:original_name: vpn_api_0040.html

.. _vpn_api_0040:

Example 1: Creating a VPN Gateway
=================================

Scenario
--------

This section describes how to create a VPN gateway by calling APIs.

Prerequisites
-------------

You have determined the region where the VPN gateway is to be deployed and obtained the endpoint for calling APIs based on the region.

You have obtained a user token if you need to use token authentication. In addition, you need to add **X-Auth-Token** to the request header when calling an API. For details about token authentication, see "Authentication" in the *Virtual Private Cloud API Reference*.

Data Preparation
----------------

.. table:: **Table 1** Key parameters in the request for creating a VPN gateway

   +----------------+----------------------------------------------------------------+--------------------------------------+
   | Parameter      | Description                                                    | Example Value                        |
   +================+================================================================+======================================+
   | vpc_id         | Specifies the ID of the VPC to which the VPN gateway connects. | cb4a631d-demo-a8df-va86-ca3fa348c36c |
   +----------------+----------------------------------------------------------------+--------------------------------------+
   | local_subnets  | Specifies a local subnet.                                      | 192.168.0.0/24,192.168.1.0/24        |
   +----------------+----------------------------------------------------------------+--------------------------------------+
   | connect_subnet | Specifies the ID of the VPC subnet used by the VPN gateway.    | f5741286-demo-a8df-va86-2c82bd9ee114 |
   +----------------+----------------------------------------------------------------+--------------------------------------+
   | eip1.id        | Specifies the ID of the active EIP used by the VPN gateway.    | cff40e5e-demo-a8df-va86-7366077bf097 |
   +----------------+----------------------------------------------------------------+--------------------------------------+
   | eip2.id        | Specifies the ID of the standby EIP used by the VPN gateway.   | d290f1ee-demo-a8df-va86-d701748f0851 |
   +----------------+----------------------------------------------------------------+--------------------------------------+

Procedure
---------

#. Create a VPN gateway associated with a VPC.

   a. Send **POST https://{endpoint}/v5/{project_id}/vpn-gateways**.

   b. Add **X-Auth-Token** to the request header.

   c. Specify the following parameters in the request body:

      ::

         {
             "vpn_gateway": {
                 "vpc_id": "cb4a631d-demo-a8df-va86-ca3fa348c36c",
                 "local_subnets": [
                     "192.168.0.0/24", "192.168.1.0/24"
                 ],
                 "connect_subnet": "f5741286-demo-a8df-va86-2c82bd9ee114",
                 "eip1": {
                     "id": "cff40e5e-demo-a8df-va86-7366077bf097"
                 },
                 "eip2": {
                     "id": "d290f1ee-demo-a8df-va86-d701748f0851"
                 }
             }
         }

   d. Check the response.

      -  The request is successful if the following response is displayed. In the response, **id** indicates a VPN gateway ID.

         .. code-block::

            {
                "vpn_gateway": {
                    "id": "620d99b8-demo-a8df-va86-200b868f2d7d",
                    "name": "vpngw-3caf",
                    "network_type": "public",
                    "attachment_type": "vpc",
                    "vpc_id": "cb4a631d-demo-a8df-va86-ca3fa348c36c",
                    "local_subnets": ["192.168.0.0/24", "192.168.1.0/24"],
                    "connect_subnet": "f5741286-demo-a8df-va86-2c82bd9ee114",
                    "bgp_asn": 64512,
                    "access_vpc_id": "cb4a631d-demo-a8df-va86-ca3fa348c36c",
                    "access_subnet_id": "f5741286-demo-a8df-va86-2c82bd9ee114",
                    "flavor": "Professional1",
                    "used_connection_number": 0,
                    "used_connection_group": 0,
                    "enterprise_project_id": "0"
                },
                "request_id": "4a739f5c-edb7-4122-b31f-b77fb1b94857"
            }

#. Query details about the VPN gateway.

   a. Send **GET https://{endpoint}/v5/{project_id}/vpn-gateways/{vgw_id}**.
   b. Add **X-Auth-Token** to the request header.
   c. Check the response.

      -  The request is successful if the following response is displayed. In the response, **id** indicates a VPN gateway ID.

         .. code-block::

            {
                "vpn_gateway": {
                    "id": "620d99b8-demo-a8df-va86-200b868f2d7d",
                    "name": "vpngw-3caf",
                    "network_type": "public",
                    "status": "ACTIVE",
                    "attachment_type": "vpc",
                    "vpc_id": "cb4a631d-demo-a8df-va86-ca3fa348c36c",
                    "local_subnets": [
                        "192.168.0.0/24", "192.168.1.0/24"
                    ],
                    "connect_subnet": "f5741286-demo-a8df-va86-2c82bd9ee114",
                    "access_vpc_id": "cb4a631d-demo-a8df-va86-ca3fa348c36c",
                    "access_subnet_id": "f5741286-demo-a8df-va86-2c82bd9ee114",
                    "bgp_asn": 64512,
                    "flavor": "Professional1",
                    "availability_zone_ids": [
                        "eu-de-01", "eu-de-02"
                    ],
                    "used_connection_number": 0,
                    "used_connection_group": 0,
                    "enterprise_project_id": "0",
                    "eip1": {
                        "id": "cff40e5e-demo-a8df-va86-7366077bf097",
                        "ip_version": 4,
                        "type": "5_bgp",
                        "ip_address": "88.***.***.8",
                        "charge_mode": "traffic",
                        "bandwidth_id": "593a1a79-demo-a8df-va86-64ec45fb23f6",
                        "bandwidth_size": 300,
                        "bandwidth_name": "vpngw-bandwidth-1391"
                    },
                    "eip2": {
                        "id": "d290f1ee-demo-a8df-va86-d701748f0851",
                        "ip_version": 4,
                        "type": "5_bgp",
                        "ip_address": "88.***.***.6",
                        "charge_mode": "traffic",
                        "bandwidth_id": "0abb9d55-demo-a8df-va86-b7500ac2a338",
                        "bandwidth_size": 300,
                        "bandwidth_name": "vpngw-bandwidth-1392"
                    },
                    "created_at": "2022-09-15T08:56:09.386Z",
                    "updated_at": "2022-09-15T11:13:13.677Z"
                },
                "request_id": "d099a7dc-ea71-45a6-a75b-dccbfe17d438"
            }
