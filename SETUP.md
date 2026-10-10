# Setting up my GrapheneOS phone, start to finish

A start-to-finish order for recreating my setup, with the settings I use. Each
step has the short version here; the linked docs have the detail. Already
running GrapheneOS? Skip step 1 and use the steps you need; none of them wipe
the phone. **Installing GrapheneOS (step 1) does wipe it, so save what you need
first.**

**Before you start**

- A [supported Pixel](https://grapheneos.org/faq#supported-devices) and a
  computer for the web installer.
- Trusted Wi-Fi.
- Your accounts and recovery codes, kept somewhere other than this phone.
- A contacts export from your old phone, plus any backups you're restoring
  (Aegis, Signal).

---

## 1. Install GrapheneOS

Use the [official web installer](https://grapheneos.org/install/web) and follow
it to the end, including locking the bootloader. On the last screen of the
phone's first setup, leave the **OEM unlocking** box checked: that turns OEM
unlocking off, so nobody can unlock the bootloader and put a different OS on
the phone without first getting in with your PIN.

## 2. First boot and lock screen

1. Finish setup in the **Owner** profile. I use three-button navigation.
2. Set a **PIN** as the screen lock.
3. **Scramble the PIN pad:** search Settings for "scramble" and turn it on. The
   digits move every time you unlock.
4. **Fingerprint plus PIN:** enroll a fingerprint, then turn on the
   **second-factor PIN** for fingerprint unlock, a separate short PIN. The
   fingerprint gets you to the PIN pad; the PIN finishes the unlock.
5. **Duress PIN and password:** **Settings > Security & privacy > Device unlock >
   Duress Password**. Set both. Entering either one at **any** prompt that asks
   for your device credentials, including the fingerprint's second-factor PIN,
   **irreversibly wipes the phone and its eSIMs**. Never test it.

Details: [Settings](docs/settings.md#lock-screen).

## 3. Obtainium, then the keyboard

1. Install [Obtainium](https://github.com/ImranR98/Obtainium/releases) from its
   GitHub release (arm64 APK). It installs and updates apps straight from their
   developers' releases, so most apps come from it from here on.
2. Install **FUTO Keyboard** through Obtainium, turn it on in
   **Settings > System > Keyboard > On-screen keyboard**, select it and type a
   test, then switch off the stock keyboard (keep the app as a fallback).

Details: [Apps](docs/apps.md#obtainium).

## 4. Contacts, two-factor codes and passwords

1. Import your contacts export in the Contacts app.
2. Install **Aegis** and restore your encrypted vault. It holds the one code
   Proton Pass can't hold for itself: Proton's own sign-in.
3. Install **Proton Pass**, sign in, and turn on autofill when it asks.

Details: [Apps](docs/apps.md#aegis-and-contacts).

## 5. Signal, before Google Play

On a fresh phone, install and register (or restore) **Signal** before installing
Google Play. I do this so Signal sets up its own background connection
instead of leaning on Google's push service. Set **Settings > Apps > Signal > App battery usage** to
**Unrestricted** so messages arrive while the phone is locked. Already have
Signal working? Leave it alone.

Details: [Apps](docs/apps.md#signal), [restoring a Signal backup](docs/backups.md#restore-signal-from-a-desktop-backup).

## 6. Sandboxed Google Play

Install it from the GrapheneOS **App Store**. It runs as ordinary sandboxed apps
with no special system access. Then lock it down:

- Play services: allow **Network** only, and set battery use to unrestricted.
  **Deny** everything else, including Notifications, Location, Contacts,
  Camera, Microphone and Sensors.
- **Reroute location requests to the OS:** on.
- In Google settings: delete the **advertising ID**, and turn off **Ad topics**,
  **App-suggested ads** and **Ad measurement**.

Details: [Sandboxed Google Play](docs/google-play.md).

## 7. The rest of the apps

| Need | App | From |
| --- | --- | --- |
| VPN | Proton VPN | Obtainium |
| Email | Proton Mail | Obtainium |
| Notes | Notesnook | Obtainium |
| Weather | Breezy Weather | Obtainium |
| Photos (self-hosted) | Immich | Obtainium |
| Media (self-hosted) | Jellyfin, Finamp | Obtainium |
| Camera | Pixel Camera | Play Store |
| Calendar | Google Calendar | Play Store |
| Maps | Google Maps | Play Store |

When the Play Store apps are in, **disable the Play Store app** (Settings >
Apps > Google Play Store > Disable) and leave Play services on. Turn the Store
back on to update, or when an app needs it for a purchase or license check.

Set **Vanadium** as the default browser (Settings > Apps > Default apps >
Browser app). Review each app's permissions as you install it (step 8).

Details: [Apps](docs/apps.md).

## 8. Lock down each app's permissions

GrapheneOS adds permissions stock Android doesn't have. Go through
**Settings > Apps > [app] > Permissions** for each app:

- **Network:** turn it off for apps that don't need the internet. My Pixel Camera
  has no network access.
- **Sensors:** off unless the app needs motion or compass data.
- **Storage Scopes:** instead of full storage access, the app sees only its own
  files plus any folders you pick.
- Everything else: allow only what a feature you actually use needs.

Details: [Apps](docs/apps.md#pixel-camera).

## 9. Network

- **2G network protection:** on, for every SIM (Settings > Network & internet >
  SIMs). Emergency calls still work.
- **Proton VPN:** **Always-on VPN** on, **Block connections without VPN** off.
- **Wi-Fi privacy:** on your trusted home network, use a randomized MAC that
  stays the same for that network; everywhere else, keep a new random MAC per
  connection.

Details: [Settings](docs/settings.md#network).

## 10. A second number

I add a cheap Tello eSIM as a **public** number for shops, sign-ups and people
I don't know well. My main line stays **private**.

| Setting | Value |
| --- | --- |
| Calls | Ask every time |
| Texts | Private line |
| Mobile data | Private line |

Details: [Two numbers](docs/two-numbers.md).

## 11. Spam calls

Install **SpamBlocker** through Obtainium. Turn on call screening and its number
database, and set it as the caller-ID and spam app. Calls are matched against
the list on the phone; only the list itself is downloaded. Then run the
[block test](docs/spam-calls.md#test-it).

Details: [Spam calls](docs/spam-calls.md).

## 12. Home screen and quiet hours

Add the **Breezy Weather** widget, turn on battery percentage and charging
optimization, and set a **Bedtime** schedule that still lets alarms through.

Details: [Settings](docs/settings.md#home-screen-and-bedtime).

## 13. Restart and check

Restart, then run through the [checklist](docs/maintenance.md#after-setup):
- unlock works;
- a Signal message arrives while the phone is locked;
- both numbers can call and text;
- the VPN reconnects;
- calendar alerts arrive with the Play Store disabled.

## 14. Back up

Open every app you want backed up, then:

1. Run **Seedvault** (Settings > System > Backup) and save its 12-word recovery
   code somewhere other than the phone.
2. Export **Aegis** (encrypted).
3. Turn on **Signal's** own backup, make one now and set a schedule; keep its
   recovery key.
4. Copy all of it **off the phone** and check the copy.

Don't rely on Seedvault alone for Aegis and Signal; keep their own backups too.

Details: [Backups](docs/backups.md).

---

**Keeping it running:** install GrapheneOS updates when offered, review updates
in Obtainium, and turn the Play Store on briefly for its apps. See
[Maintenance](docs/maintenance.md).
