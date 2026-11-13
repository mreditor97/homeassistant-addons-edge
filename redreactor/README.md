# Home Assistant App: Red Reactor Battery Monitor

Automatically control your Red Reactor Battery Monitor from within Home Assistant via MQTT.

[![Release][release-shield]][release]
![Supports aarch64 Architecture][aarch64-shield]
![Supports amd64 Architecture][amd64-shield]

## About

This app uses I2C to read the state of your Red Reactor Battery Monitor and displays the read details within Home
Assistant. The data is published to your Home Assistant instance via MQTT.

The [Red Reactor][redreactor] can be purchased to help protect your Raspberry Pi from power outages.

## WARNING! THIS IS AN EDGE VERSION!

This Home Assistant Apps repository contains edge builds of apps.
Edge builds apps are based upon the latest development version.

- They may not work at all.
- They might stop working at any time.
- They could have a negative impact on your system.

This repository was created for:

- Anybody willing to test.
- Anybody interested in trying out upcoming apps or app features.
- Developers.

If you are more interested in stable releases of our apps:

<https://github.com/mreditor97/homeassistant-apps>


[release-shield]: https://img.shields.io/badge/version-ecfc428-blue.svg
[release]: https://github.com/mreditor97/app-redreactor/tree/ecfc428
[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-no-red.svg
[redreactor]: https://www.theredreactor.com/