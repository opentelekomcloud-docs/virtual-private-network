:original_name: vpn_api_0043.html

.. _vpn_api_0043:

Example 4: Creating a VPN Connection Monitor
============================================

Scenario
--------

This section describes how to create a VPN connection monitor by calling APIs.

Prerequisites
-------------

-  You have created a VPN connection. For details, see :ref:`Creating a VPN Connection <en-us_topic_0000001854169149>`.

-  You have obtained a user token if you need to use token authentication. In addition, you need to add **X-Auth-Token** to the request header when calling an API. For details about token authentication, see "Authentication" in the *Virtual Private Cloud API Reference*.

   .. note::

      The token obtained through IAM is valid for only 24 hours. When using a token for authentication, cache it to avoid frequent calling.

Data Preparation
----------------

.. table:: **Table 1** Key parameters in the request for creating a VPN connection monitor

   +-------------------+---------------------------------------------------------+--------------------------------------+
   | Parameter         | Description                                             | Example Value                        |
   +===================+=========================================================+======================================+
   | vpn_connection_id | Specifies the ID of the VPN connection to be monitored. | cae286f2-demo-a8df-va86-e22416ca1220 |
   +-------------------+---------------------------------------------------------+--------------------------------------+

Procedure
---------

#. Create a VPN connection monitor.

   a. Send **POST https://{endpoint}/v5/{project_id}/connection-monitors**.

   b. Add **X-Auth-Token** to the request header.

   c. Specify the following parameters in the request body:

      .. code-block::

         {
             "connection_monitor": {
                 "vpn_connection_id": "cae286f2-demo-a8df-va86-e22416ca1220"
             }
         }

   d. Check the response.

      -  The request is successful if the following response is displayed. In the response, **id** indicates the ID of a VPN connection monitor.

         .. code-block::

            {
                "connection_monitor": {
                    "id": "76f64229-demo-a8df-va86-3907e2815b6d",
                    "vpn_connection_id": "cae286f2-demo-a8df-va86-e22416ca1220",
                    "type": "gateway",
                    "source_ip": "88.***.***.60",
                    "destination_ip": "192.***.***.0",
                    "proto_type": "icmp"
                },
                "request_id": "54af23d8-989e-445d-bb48-0a9da33d7f0f"
            }

#. Query details about the VPN connection monitor.

   a. Send **GET https://{endpoint}/v5/{project_id}/connection-monitors/{connection_monitor_id}**.
   b. Add **X-Auth-Token** to the request header.
   c. Check the response.

      -  The request is successful if the following response is displayed. In the response, **id** indicates the ID of a VPN connection monitor.

         .. code-block::

            {
                "connection_monitor": {
                    "id": "76f64229-demo-a8df-va86-3907e2815b6d",
                    "status": "ACTIVE",
                    "vpn_connection_id": "cae286f2-demo-a8df-va86-e22416ca1220",
                    "type": "gateway",
                    "source_ip": "88.***.***.60",
                    "destination_ip": "192.***.***.0",
                    "proto_type": "icmp"
                },
                "request_id": "72d05395-0637-4f93-9844-b4979e9d7bdc"
            }
