:original_name: vpn_08_0713.html

.. _vpn_08_0713:

Why Is Not Connected Displayed as the Status for a Successfully Created VPN Connection?
=======================================================================================

After a VPN connection is created, its status changes to **Normal** only after servers at both ends of the VPN connection communicate with each other.

-  IKE v1:

   If no traffic goes through the VPN connection for a period of time, the VPN connection needs to be renegotiated. The negotiation time depends on the value of **Lifetime (s)** in the IPsec policy. Generally, **Lifetime (s)** is set to **3600** (1 hour), indicating that the negotiation will be initiated in the fifty-fourth minute. If the negotiation succeeds, the connection remains to the next round of negotiation. If the negotiation fails, the VPN connection status changes to **Not Connected** within one hour. The connection can be restored only after the two ends of the VPN connection communicate with each other. The disconnection can be avoided by using a network monitoring tool, such as IP SLA, to generate packets.

-  IKE v2: If no traffic goes through the VPN connection for a period of time, the VPN connection remains in the connected status.
