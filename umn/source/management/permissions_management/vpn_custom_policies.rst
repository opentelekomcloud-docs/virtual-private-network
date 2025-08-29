:original_name: vpn_04_1202.html

.. _vpn_04_1202:

VPN Custom Policies
===================

Custom policies can be created to supplement the system-defined policies of VPN.

You can create custom policies in either of the following ways:

-  Visual editor: Select cloud services, actions, resources, and request conditions. This does not require knowledge of policy syntax.
-  JSON: Edit JSON policies from scratch or based on an existing policy.

For details, see `Creating a Custom Policy <https://docs.otc.t-systems.com/usermanual/iam/iam_01_0016.html>`__. The following section contains examples of common VPN custom policies.

Example VPN custom policy
-------------------------

-  Example 1: Grant permission to delete VPN gateways.

   You need to add the following dependent actions. If they are not added, an exception may occur.

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "vpn:vpnGateways:delete"
                  ]
              },
              {
                  "Effect": "Allow",
                  "Action": [
                      "vpc:subNetworkInterfaces:update",
                      "vpc:routeTables:update",
                      "vpc:subnets:delete",
                      "vpc:publicIps:list",
                      "vpc:publicIps:delete",
                      "vpc:vpcs:get",
                      "vpc:routeTables:get",
                      "vpc:ports:get",
                      "vpc:publicIps:update",
                      "vpc:subnets:get",
                      "vpc:bandwidths:list",
                      "vpc:publicIps:get",
                      "vpc:vpcs:list"
                  ]
              },
              {
                  "Effect": "Allow",
                  "Action": [
                      "er:instances:get",
                      "er:instances:list"
                  ]
              }
          ]
      }

-  Example 2: Deny VPN connection deletion.

   A policy with only "Deny" permissions must be used together with other policies. If the permissions granted to an IAM user contain both "Allow" and "Deny", the "Deny" permissions take precedence over the "Allow" permissions.

   The following method can be used if you need to assign permissions of the **VPN FullAccess** policy to a user but also forbid the user from deleting VPN connections. Create a custom policy for denying VPN connection deletion, and assign both policies to the group the user belongs to. Then the user can perform all operations on VPN except deleting VPN connections. The following is an example of a deny policy:

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Deny",
                  "Action": [
                      "vpn:vpnConnections:delete"
                  ]
              }
          ]
      }

-  Example 3: defining multiple actions in a policy

   A custom policy can contain the actions of one or multiple services that are of the same type (global or project-level). The following is an example policy containing multiple actions.

   .. code-block::

      {
          "Version": "1.1",
          "Statement": [
              {
                  "Effect": "Allow",
                  "Action": [
                      "vpn:vpnGateways:create",
                      "vpn:vpnConnections:create",
                      "vpn:customerGateways:create"
                  ]
              },
              {
                  "Effect": "Deny",
                  "Action": [
                      "vpn:vpnGateways:delete",
                      "vpn:vpnConnections:delete",
                      "vpn:customerGateways:create"
                  ]
              },
              {
                  "Effect": "Allow",
                  "Action": [
                      "vpc:vpcs:list",
                      "vpc:subnets:get"
                  ]
              }
          ]
      }
