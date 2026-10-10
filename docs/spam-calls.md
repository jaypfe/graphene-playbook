# Spam calls

Part of the [setup guide](../SETUP.md#11-spam-calls). GrapheneOS has no spam
call filtering of its own, so I use
[SpamBlocker](https://github.com/aj3423/SpamBlocker): free and open source, with
calls matched against a number list on the phone.

## Install

Add `https://github.com/aj3423/SpamBlocker` to Obtainium with the APK filter
`^app-release\.apk$` (the regular build; it needs network access to download its
list). Allow it Network.

## Set it up

| Setting | Value |
| --- | --- |
| Settings > Screening > Enable | On. Expand the row: **Call** on, **SMS** off |
| Android's caller-ID and spam app prompt | Choose SpamBlocker; keep your normal Phone app as the dialer |
| Notifications | Allow, so you can see what it blocked |
| Contacts | Allow, so your contacts always get through (Contact Scopes can limit what it sees) |
| Instant Query, Query API | Off or empty: no online lookups |
| Report Spam, Report API | Off or empty |
| Workflows > FTC-DNC | Add the preset and turn on its daily schedule |
| Quick Settings > Database | On |

The FTC-DNC preset loads 90 days of numbers people reported to the FTC, then
updates daily from the developer's
[mirror](https://github.com/aj3423/DNC_snapshot). They're complaint reports, not a
verified spam list, so the occasional real caller can get caught. Matching
happens on the phone; downloading the list still contacts the mirror.
[FTC data](https://www.ftc.gov/policy-notices/open-government/data-sets/do-not-call-data).

Run the workflow once and check the database shows a count; mine had about
570,000 numbers.

## Test it

Use a friend's number, with their OK:

1. Check their calls ring normally.
2. In SpamBlocker's **Call** tab, long-press their call. If it offers **Edit
   regex rule**, a rule for them already exists: note it down first. Otherwise
   choose **Add to regex rule**.
3. Set it to **block calls**, match their full number, apply it to both SIMs,
   and set priority **999** so your contacts list doesn't override it.
4. Use **Test** to confirm the rule matches, then have them call each of your
   numbers. It shouldn't ring, and the Call tab shows why.
5. Remove the test rule, or put back the rule you noted, and check they ring
   again.

## If something goes wrong

| Problem | Fix |
| --- | --- |
| No separate Call switch | Expand the Screening > Enable row |
| A real caller was blocked | Open their entry in the Call tab, see which rule matched, and adjust it, or switch Screening off for a moment |
| A test call still rings | Check the rule blocks (not allows), the full number, priority 999 and that it applies to both SIMs |
