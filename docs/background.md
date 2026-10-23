# Background

Four ideas show up in a home Wi-Fi assessment. This page is what each one means for a network you run. It is not a procedure for capturing traffic or guessing a key.

## WPA2 handshake

When a client joins a WPA2-Personal network, the client and the access point complete a short exchange that proves both sides know the passphrase, without sending the passphrase itself. Anyone in radio range can hear that exchange. If the passphrase is short or common, the overheard exchange can be tested against guesses later, away from your house, without joining the network again.

On a network you administer you do not need to collect that exchange. You already know whether the passphrase is weak, because you set it. The assessment is to replace a weak one and to prefer WPA3, which is built so that same offline guessing does not work against the passphrase.

## Weak passphrase

A home passphrase is the only secret on a WPA2-Personal network. Every device shares it. Length and randomness decide whether guessing is cheap. A phrase made of a pet name, a year, or a single dictionary word is a weak passphrase even when the router says "WPA2". Reusing the same phrase on email or on a second SSID means one leak covers both.

The review in the [assessment](assessment.md) scores the passphrase you configured. It does not try to recover it.

## Rogue access point

A rogue access point is a radio you did not install that is operating where your clients are. It might be a neighbour, a travel router someone plugged into your LAN, or a device brought in for a visit. The harm depends on where it sits. A radio that only advertises its own name is noise. A radio plugged into your trusted Ethernet can bypass the guest boundary you thought you had.

Monitoring is a comparison. You write down the BSSID (the radio's hardware address) of every access point you own, then look at the Wi-Fi list later and ask whether a new BSSID appeared.

## Evil twin

An evil twin advertises the same SSID as a network the client already trusts, from a different BSSID, often with weaker security or an open network and a login page. Phones and laptops join by name. If the real network is remembered, a client can attach to the copy.

Detection is the same inventory check, plus one extra question: is my SSID being announced by a BSSID that is not on my list, or with a security mode lower than the one I configured? The response is to avoid the network, confirm your own radio is still up, and forget the network on any device that joined the wrong one. If a device did join it, treat the passphrase as exposed and change it on the real access point.

## What this lab uses instead of an attack pass

| Question | How you answer it at home |
| --- | --- |
| Could a weak key be guessed from an overheard handshake? | Read the passphrase policy and replace anything short, common, or reused. |
| Is a second radio using my name? | Compare a fresh Wi-Fi scan to the BSSID inventory. |
| Did I leave an old mode enabled? | Read WPA version, WPS, and management-frame protection on the device you own. |
| Can a guest reach my laptop? | Put guests and IoT on their own SSID and turn on client isolation. |
