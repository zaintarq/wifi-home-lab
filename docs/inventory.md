# Inventory

Fill this in from the label on the device and from the router's status page. The BSSID is the value you will compare against later scans. A dual-band router usually has one BSSID per band, and sometimes a third for 6 GHz. List every one.

Do not put the passphrase in this file if you later copy the table into git. Record only whether it meets the rule in the [hardening guide](hardening.md).

| Name you use | SSID | Band | BSSID | Security you intend | Where it sits | Role |
| --- | --- | --- | --- | --- | --- | --- |
| House router | | 2.4 GHz | | WPA3-Personal | | Trusted LAN |
| House router | | 5 GHz | | WPA3-Personal | | Trusted LAN |
| House router | | 6 GHz | | WPA3-Personal | | Trusted LAN, if the router has it |
| Guest SSID | | | | WPA3-Personal | same box | Guests only |
| IoT SSID | | | | WPA2/WPA3 mixed, only if a device cannot do WPA3 | same box | Bulbs, plugs, printers |
| Spare test AP | | | | whatever you are about to change | unplugged from the trusted LAN until the review is done | Practice |

## Rules for the spare access point

- Use an SSID that is not the household name and not a neighbour's name. A suffix such as `-lab` is enough.
- Give it a passphrase that is not the household passphrase.
- Leave it unplugged from the house Ethernet until the configuration review passes. Power it from a socket only, so wireless clients of the test AP cannot walk onto the trusted LAN.
- Turn it off when you are not using it. A forgotten lab radio is a rogue AP you created yourself.

## Known-good scan

After the table is full, stand near the router and open the Wi-Fi list on a phone or laptop. Confirm each of your SSIDs is visible and that you are not already seeing your SSID twice. Two entries with the same name and different signal sources are a finding, even before you change any settings. Write the date of this first scan in the journal.
