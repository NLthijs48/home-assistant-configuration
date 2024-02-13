# [Shelly Plug S](https://www.shelly.cloud/en-nl/products/product-overview/shelly-plug-s)

Smart plug with power consumption monitoring

- Maximum loadd: 10A, 2500W
- Operating temperature: -10ºC to +50ºC
- Connection: Wi-Fi 2.4 Ghz only
- Dimensions: 46x69mm

## Setup
1. Plug into a socket
2. Connect to the shellyplug-* Wi-Fi network
3. Go to [192.168.33.1](http://192.168.33.1)
4. Configure your Wi-Fi network using the web UI
5. Find the ip address in the unifi controller
   - Has a name in a format like `shellyplug-s-000AAA`
   - Set a proper name indicating what it is used for
   - Enabled `Fixed IP address`
6. Open the shelly web UI (on the new fixed ip)
7. Configure settings:
   - `Internet & security`:
     - `Cloud`
       - Enable cloud connection to trigger firmware update
       - Disable afterwards
     - `Restrict login`: Set up the device password
     - `Advanced - Developer settings`:
       - `Enable CoIoT`:
         - `CoIoT peer`: `10.0.2.28:5683` (Home Assistant IP address)
   - `Safety`:
     - `Max power protection`: update if required for the device
   - `Settings`:
     - `Power on default mode`: choose based on the device
     - `Device name`: update
     - `Channel name`: same as `Device name` (should be detected in Home Assistant)
     - `LED light control`:
       - Disable LEDs
     - `Device reboot`: for applying developer settings and such
8. Add it in Home Assistant
   - [Should be detected already](https://my.home-assistant.io/redirect/integrations/)