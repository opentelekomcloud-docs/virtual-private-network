:original_name: vpn_faq_0055.html

.. _vpn_faq_0055:

What Do I Do If VPN Setup Fails?
================================

#. Log in to the management console and click **Virtual Private Network**.
#. In the VPN list, locate the target VPN and click **View Policy** in the **Operation** column to view IKE and IPsec policy details about the VPN.
#. Check the IKE and IPsec policies to see whether the negotiation modes and encryption algorithms between the local and remote sides of the VPN are the same.

   a. If the IKE policy has been set up during phase one and the IPsec policy has not been enabled in phase two, the IPsec policies between the local and remote sides of the VPN may be inconsistent.
   b. If the Cisco physical device is used at the customer side, it is recommended that you use MD5. Then, you need to set **Authentication Mode** to **MD5** in the IPsec policy for the VPN created on the cloud.

4. Check whether the ACL configurations are correct.

   If the subnets of your data center are 192.168.3.0/24 and 192.168.4.0/24, and the VPC subnets are 192.168.1.0/24 and 192.168.2.0/24, configure the ACL rules for each data center subnet to permit the communication with the VPC subnets. The following provides an example of ACL configurations:

   .. code-block::

      rule 1 permit ip source 192.168.3.0 0.0.0.255 destination 192.168.1.0 0.0.0.255
      rule 2 permit ip source 192.168.3.0 0.0.0.255 destination 192.168.2.0 0.0.0.255
      rule 3 permit ip source 192.168.4.0 0.0.0.255 destination 192.168.1.0 0.0.0.255
      rule 4 permit ip source 192.168.4.0 0.0.0.255 destination 192.168.2.0 0.0.0.255

5. After the configuration is complete, ping the local and the remote side from each other to check whether the VPN connection is normal.
