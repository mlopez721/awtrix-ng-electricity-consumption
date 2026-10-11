# AWTRIX NG Electricity Consumption for Home Assistant

**Author:** ML  
**Release:** 1.0

A Home Assistant automation blueprint for the Ulanzi TC002 running AWTRIX NG, communicating over MQTT. The repository provides five localized blueprint files; this README and the changelog are maintained in English.

## Available blueprints

- `awtrix_ng_electricity_consumption_en.yaml` — English
- `awtrix_ng_consumo_electrico_es.yaml` — Spanish
- `awtrix_ng_stromverbrauch_de.yaml` — German
- `awtrix_ng_consommation_electrique_fr.yaml` — French
- `awtrix_ng_consumo_eletrico_pt.yaml` — Portuguese

All five files are intended to provide the same functionality, with blueprint names, descriptions, and interface options localized. The spoken alarm remains in English, as that is the voice tested with AWTRIX NG.

## Features

- Displays current power and consumption percentage, with independent horizontal scrolling when either text does not fit.
- Uses the animated `lightningbolt` icon in a separate region.
- Configurable progress bar with a visible grey border and adjustable inner height from 1 to 6 pixels.
- Three configurable colour zones: green, yellow, and red.
- Displays percentages above 100%, while visually capping the progress bar at 100%.
- Optional text blinking at or above 100%.
- Optional alarm: RTTTL siren or English speech; only one alarm mode can be selected at a time.
- Test mode simulates 0%, 25%, 50%, 75%, and 100% at five-second intervals, including the alarm at 100% when enabled.
- Publishes on Home Assistant startup, when sensor values change, and every five seconds.

## Requirements

1. Home Assistant with MQTT configured.
2. An Ulanzi TC002 running AWTRIX NG, with a 52 × 16 pixel display.
3. A power sensor measured in watts and a consumption-percentage sensor.
4. The `lightningbolt` icon installed locally on the TC002.

## Installation

1. Download the YAML file for your preferred language.
2. In Home Assistant, open **Settings → Automations & scenes → Blueprints → Import Blueprint** and import the **raw URL** of the selected YAML file from this repository.
3. Create an automation from the imported blueprint and select the AWTRIX device and the two sensor entities.
4. If the icon is not already installed, open the AWTRIX NG web interface, go to **Icons → Add**, search for `lightningbolt` in AWTRIX Hub, and send it to AWTRIX. Confirm that its installed ID is exactly `lightningbolt` (without `.gif`).
5. Run test mode first and check the display and alarm before enabling normal operation.

The icon file is not included in this repository. Each user must download it from AWTRIX Hub to their own device.

## Official documentation

- [Home Assistant — Using automation blueprints](https://www.home-assistant.io/docs/automation/using_blueprints/)
- [AWTRIX NG documentation](https://blueforcer.github.io/awtrix-ng/)
- [AWTRIX NG — TC002 icons guide](https://blueforcer.github.io/awtrix-ng/tc002/guides/icons/)

## Release status

Version **1.0** is the initial public release. The Spanish blueprint has been tested successfully on the author's TC002. The other localized files have been prepared but should be tested on the intended Home Assistant and AWTRIX NG setup before being considered confirmed. Test your own configuration and firmware compatibility before relying on it in production.
