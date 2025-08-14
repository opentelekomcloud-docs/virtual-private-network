:original_name: vpn_08_0312.html

.. _vpn_08_0312:

How Do I Replace a Direct Connect Connection with a VPN?
========================================================

#. Ensure that the on-premises gateway supports IPsec VPN.
#. Create a VPN gateway and a VPN connection on the cloud. Select the VPC to which the Direct Connect connection uses for the VPN gateway.

   .. important::

      When creating a VPN connection, configure its remote subnet as follows to avoid routing conflicts.

      -  Delete the virtual interface of the Direct Connect connection first and then configure the VPN connection.
      -  Divide the remote subnet into two subnets and configure the VPN connection. After the Direct Connect connection is deleted, configure the VPN connection again.
