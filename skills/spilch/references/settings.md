# Settings

Settings live in the user's mailbox so every chat and scheduled run finds them: a draft with no recipient, subject `Spilch settings (keep this draft)`, body a one-line note ("Spilch settings. Don't send. Ask your assistant to change anything.") and then this JSON:

```json
{
  "version": 5,
  "uid": "u_ab12cd34ef56gh78",
  "links": ["Conveyflow"],
  "voice": { "greeting": "Hi", "signoff": "Best,\nIon", "formality": "friendly", "length": "normal" },
  "style": { "length": "short", "tone": "own", "picks": 2, "own_link": true, "wink": false },
  "send": "24h",
  "auto_send": true,
  "daily_run": { "on": false, "time": "09:00" },
  "sharing": "rich",
  "spilch_line": true,
  "email": "",
  "links_pending": false,
  "send_since": "2026-11-17",
  "history": [ { "brand": "Codeloom", "drafted": "2026-11-17", "shown": true } ],
  "last_run": ""
}
```

- `links`: just the names of the links saved with `spilch_links`, as a reminder; the Spilch server holds them (up to 3). Older settings with link objects: offer once to add them with `spilch_links`.
- `style` is the reply style; the values above are the standard. `length`: `short` (3 to 4 sentences, 40 to 70 words), `normal` (60 to 120 words) or `longer` (up to 180). `tone`: `own` (like the user's own sent emails), `formal` or `playful`. `picks`: the most Spilch picks in one reply, 1 to 3. `own_link`: add one of the user's own links when it fits the sender. `wink`: one light, kind line when the email is clearly a mass campaign. Anything else the user asks for ("warmer", "never say unfortunately", "always in Spanish") goes in `style.notes` as a short list of their own words. Settings without `style`: use the standard.
- `uid` comes only from `spilch_register`; never make one up. Without the Spilch connector save `""`; the first run that has the connector registers and saves it.
- `send` (default `24h`): `drafts` (nothing is sent; the user sends from Gmail), `24h` (sent 24 hours after drafting unless the user deleted or emptied it) or `now` (sent as soon as it's written, only for emails the user picked or labelled; pitches Spilch found on its own still wait 24 hours). Also write `auto_send` (true for `24h` or `now`) so older saved Spilch skills read it right; in older settings without `send`, `auto_send: true` means `24h`.
- `sharing`: `rich` (Company details), `facts` (Basic facts) or `minimal` (Nothing). Older settings: `share_pitch_facts: false` means `minimal`, `true` means `facts`.
- `send_since`: the date `send` was last changed; only drafts written after it are sent.
- `spilch_line`: the `Sent with /spilch` signature line, on unless the user turned it off.
- `email`: whether this mailbox is linked to the user's Spilch: `""` (not asked yet), `verified`, `pending` (the verification email was sent or drafted but `spilch_account` hasn't confirmed it) or `no` (the user declined; don't ask again). The address itself is not stored here.
- `links_pending`: true while any of the user's links is still in review, so the next run checks and tells them when one goes live.
- `history`: one entry per answered brand: `drafted` date, and `shown: true` once the user has seen it in a list or summary.
- Keep `history` to the last 100 brands.

To change settings, create a new settings draft with the full JSON (most connectors can't edit drafts), always read the newest one, and delete the old one if you can. Settings from older Spilch versions: keep their values and add the missing fields with the defaults above. If settings are missing during a scheduled run, say Spilch isn't set up in this mailbox and stop.
