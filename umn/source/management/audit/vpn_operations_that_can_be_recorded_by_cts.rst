:original_name: vpn_ug_00017.html

.. _vpn_ug_00017:

VPN Operations That Can Be Recorded by CTS
==========================================

.. table:: **Table 1** Enterprise Edition VPN-related operations that can be recorded by CTS

   =============================== ================ ===================
   Operation                       Resource Type    Trace Name
   =============================== ================ ===================
   Creating a customer gateway     customer-gateway createCgw
   Updating a customer gateway     customer-gateway updateCgw
   Deleting a customer gateway     customer-gateway deleteCgw
   Creating a VPN gateway          vpn-gateway      createVgw
   Updating a VPN gateway          vpn-gateway      updateVgw
   Deleting a VPN gateway          vpn-gateway      deleteVgw
   Updating the VPN gateway status vpn-gateway      UpdateResourceState
   Creating a VPN connection       vpn-connection   createVpnConnection
   Updating a VPN connection       vpn-connection   updateVpnConnection
   Deleting a VPN connection       vpn-connection   deleteVpnConnection
   Creating a resource tag         instance         createResourceTag
   Deleting a resource tag         instance         deleteResourceTag
   =============================== ================ ===================
