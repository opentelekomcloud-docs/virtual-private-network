:original_name: vpn_faq_00144.html

.. _vpn_faq_00144:

What Do I Do If a VPN Connection Fails to Be Established?
=========================================================

#. Log in to the management console and choose **Virtual Private Network** > **Enterprise - VPN Connections**.

#. In the VPN connection list, locate the target VPN connection, and choose **More** > **Modify Policy Settings** on the right to view IKE and IPsec policies of the VPN connection.

#. Check the IKE and IPsec policies to see whether the negotiation modes and encryption algorithms at both ends of the VPN connection are the same.

   If the IKE SA has been set up in phase 1 but no IPsec SA has been established in phase 2, the IPsec policies at both ends of the VPN connection may be inconsistent.

4. Check whether the firewall configurations are correct.

   If the subnets of your on-premises data center are 192.168.3.0/24 and 192.168.4.0/24, and the VPC subnets are 192.168.1.0/24 and 192.168.2.0/24, configure the firewall function for each on-premises subnet to allow communication with the VPC subnets. The following provides an example of firewall configurations:

   .. code-block::

      rule 1 permit ip source 192.168.3.0 0.0.0.255 destination 192.168.1.0 0.0.0.255
      rule 2 permit ip source 192.168.3.0 0.0.0.255 destination 192.168.2.0 0.0.0.255
      rule 3 permit ip source 192.168.4.0 0.0.0.255 destination 192.168.1.0 0.0.0.255
      rule 4 permit ip source 192.168.4.0 0.0.0.255 destination 192.168.2.0 0.0.0.255

5. Ping the two ends of the VPN connection from each other to check whether the VPN connection is normal.
