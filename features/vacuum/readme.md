# Vacuum: Roborock S7

This feature is for managing the Roborock S7 vacuum

- [Xiaomi Miio integration](https://www.home-assistant.io/integrations/xiaomi_miio/) to get a bunch of sensors and controls
- [Mi Home app](https://play.google.com/store/apps/details?id=com.xiaomi.smarthome&hl=en_US&gl=US) for setting up the vacuum and creating maps and such
    - Not the Roborock app, since with that one a token cannot be extracted for Home Assistant usage of the map
- [Xiaomi cloud tokens extractor program](https://github.com/PiotrMachowski/Xiaomi-cloud-tokens-extractor) for getting a token for getting the map
    - Setup done using [this guide](https://smarthomepursuits.com/how-to-setup-configure-roborock-s7-with-home-assistant/)
- [Xiaomi cloud map extractor integration](https://github.com/PiotrMachowski/Home-Assistant-custom-components-Xiaomi-Cloud-Map-Extractor) for adding a camera entity of the map
- [Xiaomi vacuum map card](https://github.com/PiotrMachowski/Home-Assistant-Lovelace-Xiaomi-Vacuum-Map-card) for control of the vacuum