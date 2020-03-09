[Manual:Switch Chip Features](https://wiki.mikrotik.com/wiki/Manual:Switch_Chip_Features)

[Manual:CRS1xx/2xx series switches](https://wiki.mikrotik.com/wiki/Manual:CRS1xx/2xx_series_switches)

[Manual:CRS3xx series switches](https://wiki.mikrotik.com/wiki/Manual:CRS3xx_series_switches)

[MTU](https://wiki.mikrotik.com/wiki/Manual:Maximum_Transmission_Unit_on_RouterBoards)

### Узнать про
- Explain what happens if the bridge has not yet learned a destination MAC address or multicast group (unknown unicast and unknown multicast flood)
- Cover that MAC learning from a wireless interface is by default taken from the registration table
- [depending on the switch chip fitted to a RouterBOARD, some of the bridge features will disable HW-offloading](https://wiki.mikrotik.com/wiki/Manual:Interface/Bridge#Bridge_Hardware_Offloading)
- Explain how some of the features that are available in the switch menu and on the switch chip don’t work when bridge HW-offloading is disabled due to selecting those specific features.
- [x] [effect of VLAN & QinQ on MTU](https://groups.geni.net/geni/wiki/QinqResults).
   В 802.1q EtherType 0x8100 и размер заголовка входит в Frame. При двух тегах Total Frame Size теперь 1500+18+4+4= 1526. MTU теперь 1500-4-4
   
   В 802.1ad EtherType Service тэга 0x8a88 и он не считается во фрейме. Total Frame Size = 1500+18+4+4= 1526. Теперь MTU 1500-0-4 
- 3 ways of doing VLANs in RouterOS and how not to mix and match them:
    1. Virtual VLAN interface (and bridging together)
    2. VLANs on switch menu (found on some units with basic switch chips)
    3. Bridge VLAN filtering
- Bridge VLAN Filtering
- ingress/egress filtering
- how to use frame-types setting with ingress filtering
- how to create a Management interface in a VLAN and how the only link between Switch and CPU is the bridge interface
- how ingress filtering works on bridge interface, this is not a global setting for bridge but for interface between switch and the CPU
- [x] why NOT to add vlan interfaces as untagged ports in a bridge, for both regular traffic and management interface: [It will cause problems if also using STP/RSTP with other vendor’s switches because BPDUs are tagged](https://wiki.mikrotik.com/wiki/Manual:Layer2_misconfiguration#VLAN_on_a_bridge_in_a_bridge)
- 