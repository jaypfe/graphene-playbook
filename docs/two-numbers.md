# Two numbers on one phone

Part of the [setup guide](../SETUP.md#10-a-second-number). I keep my main line
private and add a cheap second number for everything public: shops, sign-ups,
anyone I don't know well. If the public number gets sold, the spam lands there,
and it's easy to replace.

It doesn't make calls, texts or your location anonymous, and your carrier still
knows both lines are yours. It just keeps your main number out of the places that
leak. Dual SIM is a [Pixel feature](https://support.google.com/pixelphone/answer/9449293?hl=en),
so this works on a stock Pixel too.

## The lines

| Line | Use |
| --- | --- |
| Main line (private) | Friends, family and account recovery; mobile data |
| Tello eSIM (public) | Shops, sign-ups and anyone you don't know well |

The Tello plan I bought: 300 minutes, unlimited texts, no data, $5 per 30 days
plus a one-time $3 eSIM fee (before taxes, October 2026). Check the current
[plan](https://tello.com/buy/custom_plans?plan=0-300-unlimited) and
[eSIM fee](https://tello.com/buy/esim) before buying.

## Add the eSIM

1. On Wi-Fi, buy a **new** Tello number. Don't port your main number.
2. Turn on **Settings > Network & internet > eSIM support**, and restart if asked.
3. Temporarily switch off **SIMs > your main line > Use this SIM** (don't remove it).
4. **SIMs > Add SIM**, then scan Tello's QR code or enter its details.
5. Switch your main line back on and restart. Both lines should show.
6. Name them Private and Public, set the defaults below, and turn on
   [2G protection](settings.md#network) for the new line.

If **Add SIM** does nothing, turn eSIM support on and restart; that fixed it
for me. If it's already on, restart and try again. If activation fails, keep
your main line as it is and contact Tello support. Tello's own steps: [activate a Tello eSIM](https://tello.com/help_center/esim-install-activate/how-can-i-activate-my-tello-esim).
GrapheneOS notes: [eSIM support](https://grapheneos.org/usage#esim-support).

## Defaults

**Settings > Network & internet > SIMs:**

| Setting | Value |
| --- | --- |
| Calls | Ask every time |
| Texts (SMS) | Private line |
| Mobile data | Private line |

Both lines receive calls and texts. In a conversation you can switch the sending
line from the messaging app; check which line is selected before you send.

**Check it:**
- call and text each number from another phone;
- from each line, send a new text and make a call, and confirm the number the
  other phone sees;
- with Wi-Fi off, confirm data uses the main line.

## Voicemail

Set up the new line's voicemail by calling it from that line, then have someone
leave a message and check the notification arrives and the message plays.

## The Tello account

Use a unique password, set the account's **Security PIN** (it protects changes to
the line), and review its privacy choices. Tello asks for a contact number; giving
your main number links the two accounts, so decide what you're comfortable with.
[Tello: contact number](https://tello.com/help_center/my-account/what-is-a-contact-number-and-why-do-i-need-one).
Keep a way to recover the line if you lose the phone; an old eSIM QR code usually
can't be reused.
