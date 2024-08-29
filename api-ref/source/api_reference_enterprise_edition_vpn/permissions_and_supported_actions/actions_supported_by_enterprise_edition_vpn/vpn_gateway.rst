:original_name: vpn_api_0115.html

.. _vpn_api_0115:

VPN Gateway
===========

+----------------------------------+------------------------------------------------------+--------------------------------+------------------------------------+-------------+--------------------+
| Permission                       | API                                                  | Action                         | Dependencies                       | IAM Project | Enterprise Project |
+==================================+======================================================+================================+====================================+=============+====================+
| Creating a VPN gateway           | POST /v5/{project_id}/vpn-gateways                   | vpn:vpnGateways:create         | -  er:instances:list               | Y           | Y                  |
|                                  |                                                      |                                | -  er:instances:get                |             |                    |
|                                  |                                                      |                                | -  vpc:vpcs:list                   |             |                    |
|                                  |                                                      |                                | -  vpc:vpcs:get                    |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:get                 |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:list                |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:create              |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:delete              |             |                    |
|                                  |                                                      |                                | -  vpc:subNetworkInterfaces:update |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:create            |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:delete            |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:update            |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:get               |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:list              |             |                    |
|                                  |                                                      |                                | -  vpc:ports:create                |             |                    |
|                                  |                                                      |                                | -  vpc:bandwidths:list             |             |                    |
|                                  |                                                      |                                | -  vpc:ports:get                   |             |                    |
|                                  |                                                      |                                | -  vpc:routeTables:update          |             |                    |
|                                  |                                                      |                                | -  vpc:routeTables:get             |             |                    |
+----------------------------------+------------------------------------------------------+--------------------------------+------------------------------------+-------------+--------------------+
| Querying a VPN gateway           | GET /v5/{project_id}/vpn-gateways/{vgw_id}           | vpn:vpnGateways:get            | -  vpc:publicIps:get               | Y           | Y                  |
|                                  |                                                      |                                | -  vpc:publicIps:list              |             |                    |
|                                  |                                                      |                                | -  vpc:bandwidths:list             |             |                    |
|                                  |                                                      |                                | -  er:instances:list               |             |                    |
|                                  |                                                      |                                | -  er:instances:get                |             |                    |
|                                  |                                                      |                                | -  vpc:vpcs:list                   |             |                    |
|                                  |                                                      |                                | -  vpc:vpcs:get                    |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:get                 |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:list                |             |                    |
+----------------------------------+------------------------------------------------------+--------------------------------+------------------------------------+-------------+--------------------+
| Querying the VPN gateway list    | GET /v5/{project_id}/vpn-gateways                    | vpn:vpnGateways:list           | -  vpc:publicIps:get               | Y           | x                  |
|                                  |                                                      |                                | -  vpc:publicIps:list              |             |                    |
|                                  |                                                      |                                | -  vpc:bandwidths:list             |             |                    |
|                                  |                                                      |                                | -  er:instances:list               |             |                    |
|                                  |                                                      |                                | -  er:instances:get                |             |                    |
|                                  |                                                      |                                | -  vpc:vpcs:list                   |             |                    |
|                                  |                                                      |                                | -  vpc:vpcs:get                    |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:get                 |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:list                |             |                    |
+----------------------------------+------------------------------------------------------+--------------------------------+------------------------------------+-------------+--------------------+
| Updating a VPN gateway           | PUT /v5/{project_id}/vpn-gateways/{vgw_id}           | vpn:vpnGateways:update         | -  er:instances:list               | Y           | Y                  |
|                                  |                                                      |                                | -  er:instances:get                |             |                    |
|                                  |                                                      |                                | -  vpc:vpcs:list                   |             |                    |
|                                  |                                                      |                                | -  vpc:vpcs:get                    |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:get                 |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:list                |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:delete              |             |                    |
|                                  |                                                      |                                | -  vpc:subNetworkInterfaces:update |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:delete            |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:update            |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:get               |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:list              |             |                    |
|                                  |                                                      |                                | -  vpc:bandwidths:list             |             |                    |
|                                  |                                                      |                                | -  vpc:ports:get                   |             |                    |
|                                  |                                                      |                                | -  vpc:routeTables:update          |             |                    |
|                                  |                                                      |                                | -  vpc:routeTables:get             |             |                    |
+----------------------------------+------------------------------------------------------+--------------------------------+------------------------------------+-------------+--------------------+
| Deleting a VPN gateway           | DELETE /v5/{project_id}/vpn-gateways/{vgw_id}        | vpn:vpnGateways:delete         | -  er:instances:list               | Y           | Y                  |
|                                  |                                                      |                                | -  er:instances:get                |             |                    |
|                                  |                                                      |                                | -  vpc:vpcs:list                   |             |                    |
|                                  |                                                      |                                | -  vpc:vpcs:get                    |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:get                 |             |                    |
|                                  |                                                      |                                | -  vpc:subnets:delete              |             |                    |
|                                  |                                                      |                                | -  vpc:subNetworkInterfaces:update |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:delete            |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:update            |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:get               |             |                    |
|                                  |                                                      |                                | -  vpc:publicIps:list              |             |                    |
|                                  |                                                      |                                | -  vpc:bandwidths:list             |             |                    |
|                                  |                                                      |                                | -  vpc:ports:get                   |             |                    |
|                                  |                                                      |                                | -  vpc:routeTables:update          |             |                    |
|                                  |                                                      |                                | -  vpc:routeTables:get             |             |                    |
+----------------------------------+------------------------------------------------------+--------------------------------+------------------------------------+-------------+--------------------+
| Querying the AZs of VPN gateways | GET /v5/{project_id}/vpn-gateways/availability-zones | vpn:vpnGatewayAvailabilityZone | ``-``                              | Y           | Y                  |
+----------------------------------+------------------------------------------------------+--------------------------------+------------------------------------+-------------+--------------------+
