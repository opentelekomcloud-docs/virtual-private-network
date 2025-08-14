:original_name: vpn_faq_00041.html

.. _vpn_faq_00041:

Are a Username and Password Required for Creating an IPsec VPN Connection?
==========================================================================

No. IPsec VPN uses a pre-shared key (PSK) for authentication. The PSK is configured on a VPN gateway, and a connection will be established after VPN negotiation is complete. Therefore, no username or password is required for creating an IPsec VPN connection. Generally, SSL, PPTP, and L2TP VPNs use usernames and passwords for authentication.

.. note::

   IPsec XAUTH provides extended authentication for IPsec VPN. It requires users to enter their usernames and passwords during VPN negotiation.

   Currently, VPN does not support IPsec XAUTH.
