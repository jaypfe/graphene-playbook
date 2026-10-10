# Sandboxed Google Play

Part of the [setup guide](../SETUP.md#6-sandboxed-google-play).

GrapheneOS can run Google Play as ordinary sandboxed apps, with no special
system access and the same permission controls as any other app. It doesn't
make Google blind: what you do inside Google apps, and anything you connect to
your Google account, is still visible to Google.
[GrapheneOS docs](https://grapheneos.org/usage#sandboxed-google-play).

## Install

1. On a fresh phone, install and set up Signal first ([why](apps.md#signal)).
2. Open the GrapheneOS **App Store** in the Owner profile and install sandboxed
   Google Play. It installs the pieces it needs.
3. Apply the settings below. Its own options are under **Settings > Apps >
   Sandboxed Google Play**.
4. Install the Play Store apps you want ([list](apps.md#the-list)) and set them up.
5. **Disable the Play Store app** (Settings > Apps > Google Play Store > Disable).
   Leave **Play services** enabled.

## My settings

| Where | Setting |
| --- | --- |
| Play services: Network | Allow |
| Play services: battery | Unrestricted (allow background use) |
| Play services: everything else (Notifications, Location, Contacts, Calendar, Camera, Microphone, Sensors, and the rest) | Don't allow |
| Sandboxed Google Play settings: Reroute location requests to the OS | On |
| Sandboxed Google Play > Google Settings > Ads | Delete advertising ID |
| Ads > Ad privacy: Ad topics, App-suggested ads, Ad measurement | Off |

Denying Play services' Notifications permission only hides its own notices;
other apps' notifications don't depend on it. If an app needs one of the denied
permissions for a feature you use, allow just that one. Menu names move around
as Google updates its apps; look for the named control.

## Keeping it updated

With the Play Store disabled, its apps don't update by themselves. Every so
often, enable the Store, update, and disable it again. Also turn it on when an
app needs it for a purchase, a license check or to download content. Play
services keeps running the whole time, which is what notifications and Calendar
need. Only Play services needs the unrestricted battery setting, not the Store.
