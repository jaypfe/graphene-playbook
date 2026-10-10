# Apps

My core apps and the ones worth recommending (not everything on my phone),
where they come from, and how I set each one up. Part of the
[setup guide](../SETUP.md).

I install from each developer's own releases through Obtainium wherever I can,
and use the Play Store only for apps that need it. Never use APK mirror sites.

## The list

**Core**

| App | What it's for | Get it from | Obtainium APK filter |
| --- | --- | --- | --- |
| Obtainium | Installs and updates apps from their developers' releases | [ImranR98/Obtainium](https://github.com/ImranR98/Obtainium) | `^app-arm64-v8a-release\.apk$` |
| FUTO Keyboard | Keyboard: swipe, offline, on-device voice input | [futo-org/android-keyboard](https://github.com/futo-org/android-keyboard) | `^keyboard-.*\.apk$` |
| Aegis | Two-factor codes | [beemdevelopment/Aegis](https://github.com/beemdevelopment/Aegis) | `^aegis-.*\.apk$` |
| Proton Pass | Passwords and most two-factor codes | [Proton Pass APK page](https://protonapps.com/protonpass-android) | Direct APK link (see below) |
| Signal | Messages and calls | [signalapp/Signal-Android](https://github.com/signalapp/Signal-Android) | `^Signal-Android-github-prod-universal-release-.*\.apk$` |
| Proton VPN | VPN | [ProtonVPN/android-app](https://github.com/ProtonVPN/android-app) | `-direct-release\.apk$` |
| Proton Mail | Email | [ProtonMail/android-mail](https://github.com/ProtonMail/android-mail) | `^ProtonMail-.*\.apk$` |
| SpamBlocker | Spam call screening | [aj3423/SpamBlocker](https://github.com/aj3423/SpamBlocker) | `^app-release\.apk$` |
| Vanadium | Browser | Built into GrapheneOS | |
| Sandboxed Google Play | Google services, as ordinary apps | GrapheneOS App Store | See [Sandboxed Google Play](google-play.md) |

**Worth having**

| App | What it's for | Get it from | Obtainium APK filter |
| --- | --- | --- | --- |
| Pixel Camera | Camera (better photos than the built-in one, as of writing) | [Play Store](https://play.google.com/store/apps/details?id=com.google.android.GoogleCamera) | |
| Breezy Weather | Weather and a home-screen widget | [breezy-weather/breezy-weather](https://github.com/breezy-weather/breezy-weather) | `^breezy-weather-arm64-v8a-.*_standard\.apk$` |
| Notesnook | Notes | [streetwriters/notesnook](https://github.com/streetwriters/notesnook) | Release title `Notesnook Android`; APK `^notesnook-arm64-v8a\.apk$` |
| Google Calendar | Calendar (my calendar sync needs it) | [Play Store](https://play.google.com/store/apps/details?id=com.google.android.calendar) | |
| Google Maps | Navigation and traffic | [Play Store](https://play.google.com/store/apps/details?id=com.google.android.apps.maps) | |

**Self-hosted** (for a home server you already run)

| App | What it's for | Get it from | Obtainium APK filter |
| --- | --- | --- | --- |
| Immich | Photo backup to your own server | [immich-app/immich](https://github.com/immich-app/immich) | `^app-arm64-v8a-release\.apk$` |
| Jellyfin | Video from your media server | [jellyfin/jellyfin-android](https://github.com/jellyfin/jellyfin-android) | `-libre-release\.apk$` |
| Finamp | Music from your media server | [finamp-app/finamp](https://github.com/finamp-app/finamp) | `^app-release\.apk$`, prereleases off |

## Adding any app to Obtainium

1. **Add app**, paste the GitHub repository link (or the direct APK link).
2. Set **Filter APKs by Regular Expression** to the filter in the table, and the
   release-title filter where there is one. Leave prereleases off.
3. Check the preview picks the arm64 (or universal) APK, then install.
4. Open the app, then give it only the permissions a feature you use needs
   (see [permissions](../SETUP.md#8-lock-down-each-apps-permissions)).

If a filter stops matching after an update, look at the developer's release
files before changing it.

## Obtainium

1. Download the arm64 (or universal) APK from
   [Obtainium's releases](https://github.com/ImranR98/Obtainium/releases) and
   allow your browser to install it.
2. Allow Obtainium to install apps when Android asks.
3. Obtainium tracks its own updates; check it's in its own list.

## FUTO Keyboard

1. Install it through Obtainium right after Obtainium itself.
2. **Settings > System > Keyboard > On-screen keyboard:** enable FUTO, select it
   as the keyboard and type a test. Then switch the stock keyboard off, but keep
   the app installed as a fallback.
3. Its voice input, dictionaries and network options are your call; turn on only
   what you'll use.

## Aegis and contacts

1. Export contacts from your old phone, copy the file over through a computer,
   and import it in the Contacts app. Don't keep the export anywhere public.
2. Install Aegis and import your encrypted vault with its password.
3. Proton's own two-factor code lives in Aegis, so getting into Proton Pass
   doesn't depend on Proton Pass. Keep a Proton recovery code somewhere private
   too. Everything else goes in Proton Pass.
4. Turn on vault encryption and make an [encrypted export](backups.md#aegis).

## Proton Pass

1. In Obtainium, add the
   [official APK](https://proton.me/download/PassAndroid/ProtonPass-Android.apk)
   as a **Direct APK Link** (the source repository doesn't publish an APK).
2. Sign in once Aegis is restored, and turn on autofill when it asks. Choose
   Proton Pass as Android's autofill service if prompted.
3. Test autofill on a login form.

## Signal

1. On a fresh phone, install and register Signal **before** sandboxed Google
   Play. I do this so it sets up its own background connection rather than
   Google's push service. If Signal already works on your phone, leave it alone.
2. Restoring onto a fresh install? Follow
   [restore Signal from a desktop backup](backups.md#restore-signal-from-a-desktop-backup)
   during registration. A linked Signal Desktop isn't a backup by itself.
3. **Settings > Apps > Signal > App battery usage > Unrestricted**, and allow
   notifications.
4. Lock the phone and have someone message you to check it arrives.

## Vanadium

GrapheneOS's own browser. Set it as the default: **Settings > Apps > Default
apps > Browser app**, then check a link opens in it.

## Proton VPN

Sign in and connect, then set **Always-on VPN** on and **Block connections
without VPN** off ([network settings](settings.md#network)). Check it
reconnects after a restart.

## Pixel Camera

| Permission | My setting |
| --- | --- |
| Network | Don't allow |
| Camera, Microphone, Sensors | Allow |
| Location, Nearby devices, Notifications | Don't allow |
| Photos and videos | Storage Scopes on, with nothing added; add the DCIM/Camera folder only if it needs your existing photos |

Take a photo and open it to check.

## Immich

Sign in to your server, choose which folders to back up, and upload a test
photo to check it lands on the server.

## Jellyfin and Finamp

Use Jellyfin's **libre** build unless you need Chromecast. Sign in to your
server, allow Network and playback notifications, and test playback with the
screen off. Your server may not be reachable away from home unless you've set
that up.

## Breezy Weather, Notesnook and Proton Mail

- **Breezy Weather:** pick your weather source and location method, then add the
  widget.
- **Notesnook:** sign in and check a note syncs.
- **Proton Mail:** sign in and check a new-mail notification arrives.

## Google Calendar and Maps

- **Calendar:** add your accounts, then check an event alert arrives with the
  Play Store disabled.
- **Maps:** Location **while using the app** only.

## Any other app

Give it Network and the notifications it needs, and only the extra permissions a
feature you use requires. If a Play app won't install or says the device isn't
supported, check its account and region requirements. Don't grab the APK from a
mirror site.
