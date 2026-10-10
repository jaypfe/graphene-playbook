# Settings

The system settings I change, in the Owner profile. Part of the
[setup guide](../SETUP.md). Where a value is personal (PIN length, wallpaper,
schedule), pick your own.

## Lock screen

| Setting | Where | My value |
| --- | --- | --- |
| Navigation | Setup wizard, or Settings > System > Gestures > Navigation mode (or search Settings) | Three-button navigation |
| Screen lock | Settings > Security & privacy > Device unlock > Screen lock | PIN |
| PIN scrambling | Search Settings for "scramble" | On: the digits move every unlock |
| Fingerprint | Device unlock > Fingerprint | Enrolled |
| Second-factor PIN after fingerprint | Fingerprint settings | On, a separate PIN from the main one |
| Duress PIN and password | Device unlock > Duress Password | Both set, different from your real credentials |
| OEM unlocking | Last screen of the first setup (box checked by default) | Off: leave the box checked |
| Multiple users | Settings > System > Multiple users | Owner only |

**Duress credentials irreversibly wipe the phone and its installed eSIMs the
moment either is entered at any prompt that asks for your device credentials, including
the fingerprint's second-factor PIN. Never test them.** Store them privately, and check
your normal unlock still works after setting them.
[GrapheneOS: duress](https://grapheneos.org/features#duress),
[two-factor fingerprint unlock](https://grapheneos.org/features#two-factor-fingerprint-unlock).

Never show your PIN, fingerprint setup or recovery codes in screenshots.

## Network

| Setting | Where | My value |
| --- | --- | --- |
| 2G network protection | Settings > Network & internet > SIMs > each SIM | On ("Allow 2G" off on older versions); check each SIM, including a new eSIM |
| eSIM support | Network & internet > eSIM support | On (needed to add an eSIM) |
| Wi-Fi MAC address, trusted home network | Internet > your network > Privacy | Randomized, kept the same for that network |
| Wi-Fi MAC address, other networks | Same setting on each network | A new random MAC per connection (the default) |
| Always-on VPN | Network & internet > VPN > Proton VPN | On |
| Block connections without VPN | Same screen | Off: the phone still connects when the VPN can't |

Use one VPN at a time. SIM defaults for two numbers are in
[Two numbers](two-numbers.md#defaults). More on cellular protections:
[GrapheneOS](https://grapheneos.org/usage#carrier-functionality).

## Home screen and Bedtime

| Setting | Where | My value |
| --- | --- | --- |
| Battery percentage | Settings > Battery | On |
| Charging optimization | Settings > Battery | On (your choice of mode) |
| Wallpaper, colors, layout | Wallpaper & style | Your choice |
| Weather widget | Home screen > widgets > Breezy Weather | Time plus today's detail |
| Bedtime | Settings > Modes > Bedtime | On a schedule |
| Bedtime: turn on while charging | Bedtime settings | Off, so it follows the schedule only |
| Bedtime: what gets through | Bedtime settings | Alarms; routine notifications silenced |

To check Bedtime, turn it on by hand and make sure an alarm still sounds, then
put it back on its schedule.
