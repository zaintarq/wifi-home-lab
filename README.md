# Wi-Fi home lab

A defensive assessment for a wireless network you own: record the access points, review how they are configured, watch for a second radio using your name, then harden what you found.

The lab stops at your own router and a spare access point you control. Neighbours' networks, cafe Wi-Fi, and any SSID you do not administer are out of scope.

This repository does not include handshake capture or passphrase cracking. Those steps are left out on purpose. A weak passphrase is judged by reading the router settings and replacing it, which is the check that matters on a network you already administer.

## What you practise

| Topic | Where |
| --- | --- |
| What a handshake, a weak passphrase, a rogue AP, and an evil twin actually change | [Background](docs/background.md) |
| Write down every radio you run | [Inventory](docs/inventory.md) |
| Read the router and the test AP | [Configuration review](docs/configuration-review.md) |
| Notice a radio that is not yours | [Rogue AP and evil twin checks](docs/rogue-and-evil-twin.md) |
| WPA3, passphrases, and separate networks | [Hardening guide](docs/hardening.md) |
| Do the work in order | [Assessment](docs/assessment.md) |

## Order

1. Fill in the inventory with the BSSID printed on each of your devices.
2. Review the configuration and mark each control pass or fail.
3. Do one monitoring pass and compare it to the inventory.
4. Apply the hardening guide on the test access point first, then on the household router.
5. Repeat the configuration review and file a session note from [journal/TEMPLATE.md](journal/TEMPLATE.md).

Session notes stay local. `journal/sessions/` is gitignored so passphrases and your home address never get pushed.
