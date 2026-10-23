# Configuration review

Do this while logged into the admin page of a device you own. Prefer the spare access point for the first pass. Change the household router only after the test AP behaves the way you want.

Use the address printed on the router, from a device already on that network. If the admin page is also reachable from the mobile network, that is a finding: remote administration from the internet should be off.

Record pass or fail. Do not record the passphrase.

## Identity of the box

| Check | Pass looks like |
| --- | --- |
| Firmware | The vendor page shows this build as current, or the router has installed an update during this review |
| Admin account | The password is not printed on the sticker and is not `admin` |
| Remote admin from the WAN | Off |
| WPS | Off, including push-button and PIN |
| UPnP | Off, unless a specific device still needs it and you have written down which one |

WPS matters because a PIN path on older routers is easier to guess than a long passphrase, and it sits beside WPA2 even when the passphrase itself is fine.

## Wireless security

| Check | Pass looks like |
| --- | --- |
| Security mode | WPA3-Personal, or WPA2/WPA3 mixed only where a client cannot do WPA3 |
| Old modes | WEP, WPA, and TKIP are unavailable or off |
| Management frame protection | Required, or Capable if a client drops off when it is Required. The test AP should end on Required. |
| SSID name | Does not contain the passphrase, the street address, or the router model |
| Passphrase | Meets the rule in the [hardening guide](hardening.md), unique to this SSID |
| Band | 5 GHz or 6 GHz used for the trusted network. 2.4 GHz kept only for devices that need the range. |

If the router offers "WPA3 transition" or "WPA2/WPA3 mixed", clients that still speak only WPA2 keep the network on the weaker mode. That is acceptable for an IoT SSID and a poor end state for the trusted SSID. The hardening guide says how to split them.

## Separation

| Check | Pass looks like |
| --- | --- |
| Guest SSID | Exists, with its own passphrase |
| Guest isolation | Wireless clients on the guest SSID cannot reach each other or the trusted LAN |
| IoT SSID | Exists when a bulb, plug, or printer cannot run WPA3 or needs wide reach on 2.4 GHz |
| Trusted LAN | Phones and laptops join this SSID only |
| Ethernet | The spare test AP is not patched into the trusted switch during the review |

A guest network that uses the same passphrase as the trusted SSID has not segmented anything. The name on the menu is not the control. The separate secret and the isolation toggle are the control.

## After each fail

Fix it on the test AP, reconnect one client, and confirm the client still passes traffic. Then mark the row pass. A setting you cannot find in the menu stays fail, with the firmware version written beside it, until you replace the device or the vendor adds the control.
