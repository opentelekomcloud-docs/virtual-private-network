:original_name: vpn_01_0002.html

.. _vpn_01_0002:

Product Advantages
==================

Enterprise Edition VPN has the following advantages:

-  **High security**

   -  Data is encrypted using IKE/IPsec or SSL, ensuring high data security.
   -  A VPN gateway is exclusive to a tenant, isolating tenants from each other.

-  **High availability**

   -  A VPN gateway provides two IP addresses to establish dual independent VPN connections with a customer gateway. If one VPN connection fails, traffic can be quickly switched to the other VPN connection.
   -  Active-active gateways are deployed in different availability zones (AZs) to ensure AZ-level high availability.
   -  Active/Standby mode: In normal cases, a VPN gateway communicates with a customer gateway through the active connection. If the active connection fails, traffic is automatically switched to the standby VPN connection. After the fault is rectified, traffic is switched back to the active VPN connection.
   -  High availability (HA) mode: S2C VPN supports active/standby and active-active modes.

-  **Cost-effectiveness**

   -  IPsec connections over the Internet provide a cost-effective alternative to Direct Connect.
   -  A VPN gateway can be bound to elastic IP addresses (EIPs) that share bandwidth, reducing bandwidth costs.
   -  The bandwidth can be adjusted when an EIP instance is created.

-  **Easy to use**

   -  A VPN gateway supports multiple connection modes, including policy-based, static routing, and BGP routing, to meet different access requirements of customer gateways.
   -  A VPN gateway on the cloud can function as a VPN hub, enabling on-premises branch sites to access each other.
   -  A VPN connection can be created in a few simple steps on the VPN device in an on-premises data center and on the VPN console, and is ready to use immediately after being created.
   -  VPN can be used together with the enterprise router service, allowing enterprises to build more flexible cloud-based networks.
   -  Private VPN gateways are supported to encrypt traffic transmitted over Direct Connect connections, improving data transmission security.
   -  In S2C VPN, you can flexibly enable or disable branch interconnection to implement interconnection or isolation between customer gateways, respectively.
   -  Self-service VPN gateway upgrade is supported, allowing you to upgrade VPN gateways as required.
   -  VPN supports custom route table configurations in VPCs based on service requirements, improving network availability and flexibility.
   -  S2C VPN allows you to view the CIDR blocks negotiated by IPsec SAs and traffic monitoring statistics, facilitating fault locating.
   -  S2C VPN allows users to download the peer device's configuration file for configuration comparison.
   -  EIPs with shared bandwidth are supported, improving network resource utilization and flexibility.
