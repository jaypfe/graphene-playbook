# Backups

Part of the [setup guide](../SETUP.md#14-back-up). Three things need backing
up: the phone (Seedvault), your two-factor codes (Aegis) and Signal. Keep Aegis
and Signal's own backups too; don't rely on Seedvault alone to bring them back.
Keep backups, recovery codes and passwords somewhere other than the phone.

## Before you back up

Open every app you want backed up and finish setting it up. Some apps opt out of
system backups; for those, use the app's own export.

## Seedvault (the phone)

1. **Settings > System > Backup:** set up Seedvault.
2. Write down the **12-word recovery code** and keep it off the phone.
3. Pick a destination. A USB drive works; the phone's own storage is only a
   staging area, not a backup.
4. Turn on **Back up my apps** (and app APKs if offered), plus any folders you
   want, such as the one your Aegis export goes in.
5. **Back up now**, then read the per-app results. If an app was skipped, open
   it and retry; anything still missing needs its own export. If you export
   Aegis after the backup ran, back up again or copy the export separately.

## Aegis

1. **Aegis > Settings > Security:** make sure vault encryption is on.
2. **Import & Export > Export**, Aegis format, **Encrypt vault** checked, all
   your entries included.
3. Copy the export off the phone and keep its password separately.
4. If you can, test it by importing it on a spare device. Don't delete your
   working vault to test.

## Signal's own backup

Turn on Signal's on-device backup, create one now and set a schedule, and keep
its recovery key somewhere safe
([Signal: Android backups](https://support.signal.org/hc/en-us/articles/10066926526362-Android-On-device-Backups)).

## Restore Signal from a desktop backup

For a fresh install only. Don't wipe a working Signal to try this, and remember
a linked Signal Desktop isn't a backup by itself: make the export first.

1. Make a fresh backup from Signal Desktop
   ([Signal's steps](https://support.signal.org/hc/en-us/articles/10870366816410-Signal-Desktop-Backups))
   and keep the folder and its restore key private.
2. Copy the whole folder to the phone without renaming anything (USB in File
   transfer mode; on a Mac you may need [OpenMTP](https://openmtp.ganeshrvel.com/)).
3. In Signal's setup: **Restore or transfer > I don't have my old phone > Restore
   on-device backup**, register your number, pick the folder and enter the
   restore key. The restore key is not your Signal PIN.
4. Set up Signal's ongoing backups, then relink Signal Desktop.

## Copy everything off the phone

1. Show hidden files and copy the **whole `.SeedVaultAndroidBackup` folder**,
   hidden contents included, into a dated folder on your computer or drive.
2. Copy the Signal backup folder and the encrypted Aegis export too.
3. If your computer can't see the hidden folder over USB, copy it to a USB
   drive with the phone's Files app instead.
4. Compare file counts and sizes (checksums if you can) before deleting anything
   from the phone. Keep the previous good backup while you test a new one.

## Restoring onto a phone

1. On a replacement or rebuilt phone, install GrapheneOS
   ([official installer](https://grapheneos.org/install/)). Put the backup folder
   on storage the phone can reach.
2. In Seedvault's restore, pick the folder containing `.SeedVaultAndroidBackup`,
   choose the backup and enter the 12-word code.
3. Restore Signal and Aegis from their own backups.
4. Check accounts, contacts, photos, app data and notifications. A backup
   doesn't bring back an eSIM; if it's missing (for example on a new phone), get
   it reissued by the carrier.

[Seedvault FAQ](https://github.com/seedvault-app/seedvault/wiki/FAQ). A backup job
finishing isn't proof you can restore; test a restore on a spare phone when you
can, not on the one you use every day.
