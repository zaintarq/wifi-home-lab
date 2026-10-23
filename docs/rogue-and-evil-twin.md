# Rogue AP and evil twin checks

These checks compare what you can see in the air with the [inventory](inventory.md). They use the Wi-Fi list on a phone or laptop, or the scanner built into the router if it has one. You are looking for a radio you did not install.

Run the check in the rooms you actually use, not only beside the router. A copy of your network is easier to notice where your own signal is weak.

## Each pass

1. Read the current BSSIDs from your router status page. Confirm they still match the inventory. A firmware update can change them. Update the inventory when that happens so the next pass does not flag your own box.
2. On a phone or laptop, open the list of visible networks. Write down every row whose name matches one of your SSIDs, including the household name and the `-lab` name.
3. For each of those rows, compare the BSSID with the inventory. The phone may show it under details, or as the Wi-Fi address of the network.
4. Note the security label the phone shows: WPA3, WPA2, or Open.

## What counts as a finding

| What you see | What it means | What you do |
| --- | --- | --- |
| Your SSID, your BSSID, the security mode you set | Expected | Nothing |
| Your SSID, a BSSID that is not in the inventory | Someone else is announcing your name | Do not join it. Forget the network on any device that might prefer it. Check that your own AP is still powered. If a device has joined the unknown BSSID, change the passphrase on the real AP and reconnect only to the BSSID in the inventory. |
| Your SSID, your BSSID, but the phone shows Open or WPA where you set WPA3 | The saved network or a second radio is offering a weaker mode | Confirm the setting on the router. WPA3-only, with management frame protection required, makes a weaker copy of the same name less likely to be accepted by clients that already know the real network. |
| An SSID you do not recognise, strong signal, inside the house | A radio you did not inventory | Find the device before you call it an attack. A TV, a printer, a phone hotspot, and the spare AP left on are the usual answers. Unplug it or add it to the inventory with an owner. |
| A new wired device in the router client list that you did not plug in | A rogue AP or another host on the trusted LAN | Remove it from the port or the client list and see which switch port goes dark. Guest Wi-Fi does not fix a device that is sitting on the trusted Ethernet. |

## How often

Once when you build the inventory, again after you change SSIDs or firmware, and when a device suddenly asks you to sign in to "the home Wi-Fi" through a browser page. Your own network should not present a new login page. A page asking for the Wi-Fi password or an email password is a reason to disconnect and run this check before typing anything.

## What you record

In the journal, record the date, the rooms you walked, and whether any BSSID was missing from the inventory. You do not need a packet capture to close the check. The finding is the unexpected BSSID or the unexpected security label.
