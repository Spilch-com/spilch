# Settings

Settings live in the user's mailbox so every chat and scheduled run finds them: a draft with no recipient, subject `Spilch settings (keep this draft)`, body a one-line note ("Spilch settings. Don't send. Ask your assistant to change anything.") and then this JSON:

```json
{
  "version": 3,
  "uid": "u_ab12cd34ef56gh78",
  "links": [
    { "url": "https://cal.com/ion/intro", "for": "founders who want a quick intro call" }
  ],
  "voice": { "greeting": "Hi", "signoff": "Best,\nIon", "formality": "friendly", "length": "normal" },
  "send": "drafts",
  "auto_send": false,
  "daily_run": { "on": false, "time": "09:00" },
  "sharing": "rich",
  "spilch_line": true,
  "send_since": "2026-11-17",
  "history": [ { "brand": "Codeloom", "drafted": "2026-11-17", "shown": true } ],
  "last_run": ""
}
```

- `uid` comes only from `spilch_register`; never make one up. Without the Spilch connector save `""`; the first run that has the connector registers and saves it.
- `send`: `drafts` (nothing is sent; the user sends from Gmail), `24h` (sent 24 hours after drafting unless the user deleted or emptied it) or `now` (sent as soon as it's written, only for emails the user picked or labelled; pitches Spilch found on its own still wait 24 hours). Also write `auto_send` (true for `24h` or `now`) so older saved Spilch skills read it right; in older settings without `send`, `auto_send: true` means `24h`.
- `sharing`: `rich` (Company details), `facts` (Basic facts) or `minimal` (Nothing). Older settings: `share_pitch_facts: false` means `minimal`, `true` means `facts`.
- `send_since`: the date `send` was last changed; only drafts written after it are sent.
- `spilch_line`: the `Sent with /spilch` signature line, on unless the user turned it off.
- `history`: one entry per answered brand: `drafted` date, and `shown: true` once the user has seen it in a list or summary.
- Keep `history` to the last 100 brands.

To change settings, create a new settings draft with the full JSON (most connectors can't edit drafts), always read the newest one, and delete the old one if you can. Settings from older Spilch versions: keep their values and add the missing fields with the defaults above. If settings are missing during a scheduled run, say Spilch isn't set up in this mailbox and stop.
