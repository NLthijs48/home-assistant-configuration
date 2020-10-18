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
    

