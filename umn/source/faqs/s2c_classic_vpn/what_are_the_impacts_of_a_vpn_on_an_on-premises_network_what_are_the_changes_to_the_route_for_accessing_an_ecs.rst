:original_name: vpn_08_0325.html

.. _vpn_08_0325:

What Are the Impacts of a VPN on an On-premises Network? What Are the Changes to the Route for Accessing an ECS?
================================================================================================================

When you configure a VPN, perform the following operations on the on-premises gateway:

#. Configure IKE and IPsec policies.
#. Specify the to-be-protected traffic (firewall).
#. Check the route configuration on the gateway to ensure that traffic destined for a VPC can be routed to the correct outbound interface (interface having an IPsec policy bound).

After the VPN configuration is complete, only the traffic matching the ACL rules enters the VPN tunnel.

For example, before a VPN is created, on-premises users access the ECS through the EIP bound to the ECS. After a VPN is created, data flows matching the firewall rules access the private IP address of the ECS through the VPN tunnel.
