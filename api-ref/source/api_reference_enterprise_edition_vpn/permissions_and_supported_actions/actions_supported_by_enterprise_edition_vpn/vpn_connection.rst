:original_name: vpn_api_0117.html

.. _vpn_api_0117:

VPN Connection
==============

+-----------------------------------------+------------------------------------------------------------+---------------------------+----------------------------------------+-------------+--------------------+
| Permission                              | API                                                        | Action                    | Dependencies                           | IAM Project | Enterprise Project |
+=========================================+============================================================+===========================+========================================+=============+====================+
| Creating a VPN connection               | POST /v5/{project_id}/vpn-connection                       | vpn:vpnConnections:create | ces:metricData:list                    | Y           | Y                  |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | ces:currentRegionSupportedMetrics:list |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:vpcs:list                          |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:vpcs:get                           |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subnets:get                        |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subnets:list                       |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subNetworkInterfaces:update        |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:publicIps:get                      |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:publicIps:list                     |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:bandwidths:list                    |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:ports:get                          |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:routeTables:update                 |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:routeTables:get                    |             |                    |
+-----------------------------------------+------------------------------------------------------------+---------------------------+----------------------------------------+-------------+--------------------+
| Querying the VPN connection list        | GET /v5/{project_id}/vpn-connection                        | vpn:vpnConnections:list   | vpc:publicIps:get                      | Y           | x                  |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:publicIps:list                     |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:bandwidths:list                    |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | er:instances:list                      |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | er:instances:get                       |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:vpcs:list                          |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:vpcs:get                           |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subnets:get                        |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subnets:list                       |             |                    |
+-----------------------------------------+------------------------------------------------------------+---------------------------+----------------------------------------+-------------+--------------------+
| Querying details about a VPN connection | GET /v5/{project_id}/vpn-connection/{vpn_connection_id}    | vpn:vpnConnections:get    | vpc:publicIps:get                      | Y           | Y                  |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:publicIps:list                     |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:bandwidths:list                    |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | er:instances:list                      |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | er:instances:get                       |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:vpcs:list                          |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:vpcs:get                           |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subnets:get                        |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subnets:list                       |             |                    |
+-----------------------------------------+------------------------------------------------------------+---------------------------+----------------------------------------+-------------+--------------------+
| Updating a VPN connection               | PUT /v5/{project_id}/vpn-connection/{vpn_connection_id}    | vpn:vpnConnections:update | vpc:vpcs:list                          | Y           | Y                  |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:vpcs:get                           |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subnets:get                        |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subnets:list                       |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subNetworkInterfaces:update        |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:publicIps:get                      |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:publicIps:list                     |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:bandwidths:list                    |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:ports:get                          |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:routeTables:update                 |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:routeTables:get                    |             |                    |
+-----------------------------------------+------------------------------------------------------------+---------------------------+----------------------------------------+-------------+--------------------+
| Deleting a VPN connection               | DELETE /v5/{project_id}/vpn-connection/{vpn_connection_id} | vpn:vpnConnections:delete | ces:metricData:list                    | Y           | Y                  |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | ces:currentRegionSupportedMetrics:list |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:vpcs:list                          |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:vpcs:get                           |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subnets:get                        |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:subNetworkInterfaces:update        |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:publicIps:get                      |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:publicIps:list                     |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:bandwidths:list                    |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:ports:get                          |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:routeTables:update                 |             |                    |
|                                         |                                                            |                           |                                        |             |                    |
|                                         |                                                            |                           | vpc:routeTables:get                    |             |                    |
+-----------------------------------------+------------------------------------------------------------+---------------------------+----------------------------------------+-------------+--------------------+
