# Thijs' home assistant configuration

This repository contains all automations and UI that makes my house smart, as well as all other YAML-defined things like integrations.

### Organization of the repository

- `api/` Couple of HTTP requests for use in Intellij IDEA, so that I have an easy 'check config' and 'restart' button in my editor
- `features/` Packages that handle a specific feature of my house, including all setup, automations and UI
- `ui/` Generic UI components that do not belong to one of the features (yet)
- `www/` Frontend files to be used in Lovelace dashboards
- `.gitignore` Prevents some files to be included in this repository, like secrets.yaml
- `configuration.yaml` Main Home Assistant configuration file, ties everything together (trying to put as little as possible in this file, integration setup is usually located in one of the features)
- `lovelace_resources.yaml` List of custom Lovelace cards installed using HACS (sadly this needs to be manually defined if using a yaml Lovelace dashboard)
- `ui-lovelace.yaml` Definition of all (YAML-defined) dashboards
    - Only does high-level layouting, just including cards from one of the `features/` folders
    - Contains some templates for the button-card component, apparently that can only be defined here
    
# Hardware
- Raspberry Pi 4 Model B - 4GB
- [Samsung 850 EVO 500gb](https://www.samsung.com/nl/business/memory-storage/sata-ssd/850-evo-sata-3-2-5-inch-ssd-mz-75e500b-eu/) ssd
  - The database is stored on here, the HA operating system is on the SD card 
- [Sitecom USB 3.0 hub 4 port](https://www.sitecom.com/nl/usb-30-hub-4-port/cn-083/p/1721)
  - Used to connect the SSD, actively powered to prevent overloading the power supply of the Raspberry pi itself
- [Ewent USB 3.2 to 2.5 inch SATA Hard Drive Adapter Cable for SSD / HDD](https://www.ewent.com/en-us/2-5-sata-hdd-ssd-to-usb-adapter-cable-ew7017)
  - Used to connect the SSD to the USB hub