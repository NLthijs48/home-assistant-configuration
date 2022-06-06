# Home cinema

This feature sets up integration with my TV (Philips 65PUS6503) and receiver (Onkyo TX-NR709).
It offers easy to use buttons to switch between sources, which in turn updates the input of the TV and input of the receiver.

### Hardware
- [Onkyo TX-NR709](https://tweakers.net/pricewatch/286763/onkyo-tx-nr709/specificaties/) receiver
- Set of [Hepta](https://www.hepta.nl/) Street Gold speakers 
- [Marmitek BoomBoom 100](https://marmitek.com/products/boomboom-100-bluetooth-transmitter-receiver-in-1) bluetooth receiver
  - Connected to the receiver to connected devices over bluetooth
- [Philips 65PUS6503](https://www.philips.nl/c-p/65PUS6503_12/6500-series-ultraslanke-4k-uhd-led-smart-tv) TV
  - Has an api that breaks after ~10 calls, pretty useless (HDMI control works though)
- [Chromecast 4K](https://store.google.com/product/chromecast)

### Software
- [Onkyo](https://www.home-assistant.io/integrations/onkyo/) integration
- HA phone app to detect connected bluetooth device and select that input on the receiver
- [Chromecast integration](https://www.home-assistant.io/integrations/cast/)
- [Spotify integration](https://www.home-assistant.io/integrations/spotify)
  - Play music, and show playlist UI

### HDM-CEC setup

Home Assistant does not support using the [HDMI-CEC plugin](https://www.home-assistant.io/integrations/hdmi_cec/) directly on the Raspberry Pi 4 anymore, since they don't want to maintain custom drivers for it.

But I'm using a workaround for that:
1. Added an extra supervisor addon repository: https://github.com/samueltardieu/homeassistant-addons
2. Installed the HDMI-CEC addon: https://github.com/samueltardieu/homeassistant-addon-pi-cec
3. Started the addon
4. Configured the HDMI-CEC plugin to use the local hostname of the addon as host, which means it talks to it using TCP locally 

### Receiver cables
- Power cable
- `HDMI Out main` to the TV (supports ARC)
- `HDMI 1 BD/DVD` to the Steam Link
- `HDMI 3 CBL/SAT` to the T-Mobile TV box
- `HDMI 5 PC` 
- `HDMI 7` to the Raspberry Pi (for HDMI CEC and log messages)
- `Optical 1 Game` to the bluetooth receiver (Marmitek BoomBoom 100)
- `Pre out Front` to the bluetooth sender (Marmitek BoomBoom 100)
- `Pre out subwoofer` to the active subwoofer
- `Front R` + `Front L` to the speakers

### Receiver settings

There is something wrong with my Onkyo receiver which causes it to lose its settings when it is disconnected from
electricity.
Would be cool to use the network control commands to setup all these settings: https://github.com/miracle2k/onkyo-eiscp

The following settings needs to be entered again:
1. Input output
    1. Monitor out: hdmi main
        1. Resolution auto
    2. Hdmi input
        1. Bd/dvd: 1
        2. Vcr/dvr: 2
        3. Cbl/sat: 3
        4. Game: 4
        5. Pc: 7
2. Speaker setup:
    1. Speaker settings:
        1. 4 ohm
        2. Speakers type (front): normal
    2. Speaker configuration:
        1. Subwoofer yes
        2. Front 80hz
    3. Equalizer:
        1. Manual
        2. Channel: front
            1. 63hz: +2
            2. 160hz: +1
        3. Channel: subwoofer
            1. 25hz: +2
            2. 40hz: +3
            3. 63hz: +3
            4. 100hz: +2
            5. 160hz: +1
        4. Thx:
            1. Thx ultra2/select2 subwoofer: no
            2. Loudness plus: on
3. Audio adjust: nothing
4. Source setup:
    1. Names
5. Presets
6. Miscellaneous:
    1. Volume setup
        1. Absolute
        2. Power on volume 40
7. Hardware setup
    1. Hdmi:
        1. Hdmi control: on
        2. Arc on
    2. Network:
        1. DHCP, unifi gives it the same ip again: 10.0.2.1
        2. Network control: enable
