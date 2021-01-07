# Computer

This package integrates computers and laptops, containing these features:
integrations/wake_on_lan/) integration)

- Provide switches to turn computers on and off
    - Uses [wake on lan](https://www.home-assistant.io/integrations/wake_on_lan/) for turning on
    - Which also pings the computers regularly to track if they are online (affecting presence and lighting)
    - Uses [IOTlink](https://iotlink.gitlab.io/) for turning off (sleep)
- Get statistics from my computer (using IOTLink)
- Notifications to my computer (using IOTLink)
