# Network

Sets up network related monitoring and automations.

### Hardware
- Fiber connection with 500Mbps service from T-Mobile
- [Unifi Security Gateway](https://store.ui.com/products/unifi-security-gateway)
    - As modem for the incoming fiber
    - As router + NAT
    - As DHCP server
- 2x [UAP-AC-Lite](https://store.ui.com/products/unifi-ac-lite) as access points on the ground floor and first floor.
- [TP-Link TL-SG1016DE](https://www.tp-link.com/nl/business-networking/easy-smart-switch/tl-sg1016de/) switch
    - Connects to devices in the utility closet
    - Connects to wall sockets through the house

### Software
- [Unifi network application Add-on](https://github.com/hassio-addons/addon-unifi) as the Unifi controller
    - Runs on the Raspberry Pi like HASS OS
    - SSH into devices and use `set-inform http://10.0.2.28:8880/inform` to connect them
- [Unifi integration](https://www.home-assistant.io/integrations/unifi/)
    - Creates device trackers to know which devices are home, and on which floor 
