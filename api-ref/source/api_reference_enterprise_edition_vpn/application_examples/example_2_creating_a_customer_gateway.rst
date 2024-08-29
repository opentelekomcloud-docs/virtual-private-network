:original_name: vpn_api_0041.html

.. _vpn_api_0041:

Example 2: Creating a Customer Gateway
======================================

Scenario
--------

This section describes how to create a customer gateway by calling APIs.

Prerequisites
-------------

You have obtained a user token if you need to use token authentication. In addition, you need to add **X-Auth-Token** to the request header when calling an API. For details about token authentication, see "Authentication" in the *Virtual Private Cloud API Reference*.

Data Preparation
----------------

.. table:: **Table 1** Key parameters in the request for creating a customer gateway

   +------------+---------------------------------------------------+----------------------------+
   | Parameter  | Description                                       | Example Value              |
   +============+===================================================+============================+
   | name       | Specifies a customer gateway name.                | stub-customer-gateway-id-1 |
   +------------+---------------------------------------------------+----------------------------+
   | route_mode | Specifies the gateway routing mode.               | static                     |
   +------------+---------------------------------------------------+----------------------------+
   | ip         | Specifies the IP address of the customer gateway. | 10.12.13.21                |
   +------------+---------------------------------------------------+----------------------------+

Procedure
---------

#. Create a customer gateway.

   a. Send **POST https://{endpoint}/v5/{project_id}/customer-gateways**.

   b. Add **X-Auth-Token** to the request header.

   c. Specify the following parameters in the request body:

      .. code-block::

         {
             "customer_gateway": {
                 "name": "cgw-3ebf",
                 "id_type": "ip",
                 "id_value": "10.***.***.21"
             }
         }

   d. Check the response.

      -  The request is successful if the following response is displayed. In the response, **id** indicates a customer gateway ID.

         ::

            {
                "customer_gateway": {
                    "id": "03c0aa3d-demo-a8df-va86-9d82473765d4",
                    "name": "cgw-3ebf",
                    "id_type": "ip",
                    "id_value": "10.***.***.21",
                    "created_at": "2024-06-25T13:19:37.335+02:00",
                    "updated_at": "2024-06-25T13:19:37.335+02:00"
                },
                "request_id": "e55783ba-5cc8-40c1-ad81-12cce6f773d2"
            }

#. Query details about the customer gateway.

   a. Send **GET https://{endpoint}/v5/{project_id}/customer-gateways/{customer_gateway_id}**.
   b. Add **X-Auth-Token** to the request header.
   c. Check the response.

      -  The request is successful if the following response is displayed. In the response, **id** indicates a customer gateway ID.

         ::

            {
                "customer_gateway": {
                    "id": "03c0aa3d-demo-a8df-va86-9d82473765d4",
                    "name": "cgw-3ebf",
                    "id_type": "ip",
                    "id_value": "10.***.***.21",
                    "created_at": "2024-06-25T13:19:37.335Z",
                    "updated_at": "2024-06-25T13:19:37.335Z"
                },
                "request_id": "8cf476c4-c3d4-4516-bfbc-01e2473e549b"
            }
