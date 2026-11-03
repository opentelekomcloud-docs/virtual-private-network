:original_name: vpn_ug_00017.html

.. _vpn_ug_00017:

Key Operations That Can Be Recorded by CTS
==========================================

.. table:: **Table 1** Operations related to S2C Enterprise Edition VPN that can be recorded by CTS

   +---------------------------------------------------------+--------------------+--------------------------------+
   | Operation                                               | Resource Type      | Trace Name                     |
   +=========================================================+====================+================================+
   | Creating a customer gateway                             | customer-gateway   | createCgw                      |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Updating a customer gateway                             | customer-gateway   | updateCgw                      |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Deleting a customer gateway                             | customer-gateway   | deleteCgw                      |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Creating a VPN gateway                                  | vpn-gateway        | createVgw                      |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Updating a VPN gateway                                  | vpn-gateway        | updateVgw                      |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Deleting a VPN gateway                                  | vpn-gateway        | deleteVgw                      |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Updating the specification of a pay-per-use VPN gateway | vpn-gateway        | updatePostpaidVgwSpecification |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Creating a VPN connection                               | vpn-connection     | createVpnConnection            |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Updating a VPN connection                               | vpn-connection     | updateVpnConnection            |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Deleting a VPN connection                               | vpn-connection     | deleteVpnConnection            |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Creating a resource tag                                 | instance           | batchCreateResourceTags        |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Deleting a resource tag                                 | instance           | batchDeleteResourceTags        |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying the customer gateway list                      | customer-gateway   | listCgws                       |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying a customer gateway                             | customer-gateway   | showCgw                        |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying resource tags                                  | instance           | showResourceTags               |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying project tags                                   | instance           | listProjectTags                |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying resource instances by tag                      | instance           | listResourcesByTags            |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying the number of resource instances by tag        | instance           | countResourcesByTags           |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying a VPN gateway                                  | vpn-gateway        | showVgw                        |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying the AZs of VPN gateways                        | availability_zone  | listAvailabilityZones          |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying the AZs of VPN gateways                        | availability_zone  | listExtendedAvailabilityZones  |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying the VPN connection list                        | vpn-connection     | listVpnConnections             |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying a VPN connection                               | vpn-connection     | showVpnConnection              |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying the VPN gateway list                           | vpn-gateway        | listVgws                       |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying a VPN connection monitor                       | connection-monitor | showConnectionMonitor          |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying the VPN connection monitor list                | connection-monitor | listConnectionMonitors         |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying quotas of a specified tenant                   | quota              | showQuotasInfo                 |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Querying VPN connection logs                            | vpn-connection     | showVpnConnectionLog           |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Creating VPN connections in batches                     | vpn-connection     | batchCreateVpnConnection       |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Creating a VPN connection monitor                       | connection-monitor | createConnectionMonitor        |
   +---------------------------------------------------------+--------------------+--------------------------------+
   | Deleting a VPN connection monitor                       | connection-monitor | deleteConnectionMonitor        |
   +---------------------------------------------------------+--------------------+--------------------------------+
