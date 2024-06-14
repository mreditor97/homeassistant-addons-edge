# Home Assistant Add-on: Cloudflare Dynamic DNS Updater

Automatically update your Cloudflare DNS IP address with integrated HTTPS support via Let's Encrypt.

[![Release][release-shield]][release]
![Supports aarch64 Architecture][aarch64-shield]
![Supports armhf Architecture][armhf-shield]
![Supports armv7 Architecture][armv7-shield]
![Supports amd64 Architecture][amd64-shield]
![Supports i386 Architecture][i386-shield]

## About

This add-on updates your DNS records that are hosted on [Cloudflare][cloudflare] to an IP address of your choice.
It includes the support for creating and renewing your Let's Encrypt certificate automatically.

**You must have a account with Cloudflare and must have a Cloudflare API key before being able to use this addon.**

*This is a modified version of [mrmichaelrb's][mrmichaelrb] GoDaddy Dynamic DNS Updater - so all credit goes to him! Thanks!*

## WARNING! THIS IS AN EDGE VERSION!

This Home Assistant Add-ons repository contains edge builds of add-ons.
Edge builds add-ons are based upon the latest development version.

- They may not work at all.
- They might stop working at any time.
- They could have a negative impact on your system.

This repository was created for:

- Anybody willing to test.
- Anybody interested in trying out upcoming add-ons or add-on features.
- Developers.

If you are more interested in stable releases of our add-ons:

<https://github.com/mreditor97/homeassistant-addons>


[release-shield]: https://img.shields.io/badge/version-c7a7ab5-blue.svg
[release]: https://github.com/mreditor97/addon-ddns-cloudflare/tree/c7a7ab5
[aarch64-shield]: https://img.shields.io/badge/aarch64-yes-green.svg
[armhf-shield]: https://img.shields.io/badge/armhf-yes-green.svg
[armv7-shield]: https://img.shields.io/badge/armv7-yes-green.svg
[amd64-shield]: https://img.shields.io/badge/amd64-yes-green.svg
[i386-shield]: https://img.shields.io/badge/i386-yes-green.svg
[cloudflare]: https://www.cloudflare.com
[mrmichaelrb]: https://github.com/mrmichaelrb/hassio-addons