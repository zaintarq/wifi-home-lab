# Assessment

Run this on equipment you own. The spare access point takes the first change. The household router moves only when the test client still works.

## 0. Scope

- List the router and the test AP in the [inventory](inventory.md), including every BSSID.
- Give the test AP an SSID that is not your household name.
- Leave the test AP off the trusted Ethernet.

Stop if you cannot say who owns a network you are about to join or reconfigure.

## 1. Read the configuration

Walk the [configuration review](configuration-review.md) on the test AP. Mark each row pass or fail in the journal. Fix fails on the test AP before you touch the house router.

The passphrase check is a review of what you set: length, randomness, and uniqueness across SSIDs. You are not trying to recover a passphrase from traffic.

## 2. Look for radios you did not install

Follow [rogue AP and evil twin checks](rogue-and-evil-twin.md). One pass through the rooms is enough for this assessment. A BSSID of your SSID that is absent from the inventory is a finding. A printer hotspot you forgot is also a finding until you turn it off or inventory it.

## 3. Harden

Follow the [hardening guide](hardening.md) on the test AP:

- WPA3-Personal, management frame protection required
- WPS off
- a new passphrase that meets the length rule and is not reused
- no path from this AP onto the trusted LAN

Reconnect one client. Confirm it shows WPA3 and can pass traffic.

## 4. Move the same standard to the house router

Create or repair the trusted, guest, and IoT split. Turn on guest isolation. Confirm a guest client cannot open the router admin page.

Repeat the room walk. Update the inventory if firmware changed a BSSID.

## 5. Close the note

The journal entry for the day should let you answer, a month later:

- Which firmware was running
- Whether WPS was off
- Whether the trusted SSID was WPA3
- Whether any unexpected BSSID was announcing your name
- Which exceptions remain, and which device forces each one

Power the test AP off when the note is written.
