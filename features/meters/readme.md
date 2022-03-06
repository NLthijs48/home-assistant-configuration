# Meters

Implements a vertical LED strip display to show the value of a sensor visually.

### Hardware
- [QuinLED Dig UNO LED controller](https://quinled.info/pre-assembled-quinled-dig-uno/) that runs [WLED](https://github.com/Aircoookie/WLED)
- [WS2815 12V 1m 144 LED strip](https://www.btf-lighting.com/collections/ws2815-12v/products/1-ws2815-dc12v-led-pixels-strip-light-dual-signal?variant=25774562345060)
- [1 meter aluminium profile with round frosted cover](https://www.ledprofielkoning.nl/opbouw-ledstripprofielen/led-profiel-1-meter-opbouw-breed-19-mm-ronde-afdekkap/)
- 12V power brick (Dig UNO uses that, and does passthrough to the LED strip)

### Software
- [WLED](https://github.com/Aircoookie/WLED) on the LED controller
- No WLED Home Assistant integration (at least not for this feature itself)
  - WLED only allows splitting up strips into a maximum of 16 segments, which are each separate `light` entities in Home Assistant. That means it is not possible to show a precise meter result on the strip though, only in 1/16 pieces of the strip
- Using the [WLED json api](https://kno.wled.ge/interfaces/json-api/#per-segment-individual-led-control) 'Per segment individual LED control' option to set the correct LEDs.

### UI
- The meter (and therefore strip) is split into pieces with different colors, for my CO2 meter the bottom half is green, next quarter orange, last quarter red.
- The range of the meter is set by specifying a start and end value, representing the bottom and top of the strip.

### Lighting strategy
From the bottom of the strip to the top:
- All leds below the current sensor value are lit 'normally'
- A couple of LEDS around the current sensor value are lit 'bright'
- All remaining LEDS are lit dimly, just enough to make out their color

### Brightness
- The whole meter can be scaled to be brighter or more dim, so that it can be adjusted to the time of day (and therefore ambient light levels).