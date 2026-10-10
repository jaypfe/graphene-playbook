# Checks and maintenance

Part of the [setup guide](../SETUP.md#13-restart-and-check).

## After setup

Restart, then check:

- [ ] PIN and fingerprint-plus-PIN unlock work after the restart. Don't touch the duress credentials.
- [ ] FUTO is the keyboard; your contacts and Aegis codes are there.
- [ ] Proton Pass autofills a login.
- [ ] Links open in Vanadium.
- [ ] The VPN reconnects on its own.
- [ ] A Signal message arrives while the phone is locked.
- [ ] Google Calendar alerts arrive with the Play Store disabled.
- [ ] Pixel Camera takes and opens a photo with Network denied.
- [ ] Both numbers can call and text, and outgoing calls and texts use the line you expect ([defaults](two-numbers.md#defaults)).
- [ ] The public line's voicemail notifies you.
- [ ] SpamBlocker blocks a test rule, and calls ring again once it's removed or the previous rule is restored ([test](spam-calls.md#test-it)).
- [ ] Backups are copied off the phone ([backups](backups.md)).

## Keeping it up to date

| When | Do | Then check |
| --- | --- | --- |
| A GrapheneOS update is offered | Install it and restart | Unlock and connectivity work |
| Every so often | Review updates in Obtainium | Updated apps open; their sources still match |
| Every so often | Enable the Play Store, update its apps, disable it again | Calendar and notifications still work |
| Tello renewal | Check the plan and balance | Both numbers still work |
| Every so often | Look at SpamBlocker's workflow result | The list is fresh, not just large |
| You change app data or two-factor codes | Refresh backups and exports | They're copied off the phone |
| You change an app's permissions | Test the feature and its notifications | |

## When something breaks

| Problem | Fix |
| --- | --- |
| **Add SIM** does nothing | Turn on eSIM support and restart ([two numbers](two-numbers.md#add-the-esim)) |
| No voicemail notification on the new line | Set up its mailbox, then test with a fresh message |
| Real calls are being blocked | Check which SpamBlocker rule matched and fix it ([spam calls](spam-calls.md#if-something-goes-wrong)) |
| An app's notifications don't arrive | Check its notification permission and battery setting; Play-based apps also need Play services running |
| Lost or reset the phone | Restore from your backups ([restoring](backups.md#restoring-onto-a-phone)); if the eSIM is missing, get it reissued by the carrier |
