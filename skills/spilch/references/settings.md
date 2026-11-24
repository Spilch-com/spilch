# Settings

Settings live on the user's Spilch account, so every chat, assistant and scheduled run reads the same ones. Read them with `spilch_settings` (no arguments) and change them with `spilch_settings`, action `set`, passing only the keys that change. A key set to `null` is removed.

```json
{
  "send": "24h",
  "send_since": "2026-11-24T13:05:20Z",
  "daily_run": { "on": false, "time": "09:00" },
  "sharing": "rich",
  "spilch_line": true,
  "configured": true,
  "voice": { "greeting": "Hi", "signoff": "Best,\nIon", "formality": "friendly" },
  "style": { "length": "short", "tone": "own", "picks": 2, "own_link": true, "wink": false },
  "links_pending": false,
  "history": [ { "thread": "18c2f0a9b1d4e7aa", "brand": "Codeloom", "drafted": "2026-11-24T10:12:00Z", "shown": true } ],
  "last_run": "2026-11-24T10:15:00Z"
}
```

## Chosen by the user at sign-in

The user picks these four on Spilch's sign-in page when they add the connector, and can change them in chat any time.

- `send` (default `24h`): `drafts` (nothing is sent; the user sends from their mail), `24h` (sent 24 hours after drafting unless the user deleted or emptied it) or `now` (sent as soon as it's written, only for emails the user picked or labelled; pitches Spilch found on its own still wait 24 hours).
- `daily_run`: the morning check, `on` and a 24-hour `time`.
- `sharing`: `rich` (Company profile), `facts` (Name and pitch) or `minimal` (Nothing).
- `spilch_line`: the `Sent with /spilch` signature line.

`send_since` and `configured` are kept by Spilch: `send_since` is the moment `send` last changed (only drafts written after it are sent), and `configured` is true once the user has saved the sign-in page. Don't set either.

## Kept by you between runs

- `voice`: greeting, sign-off and formality, read from the user's own sent mail.
- `style`: the reply style; the values above are the standard. `length`: `short` (3 to 4 sentences, 40 to 70 words), `normal` (60 to 120 words) or `longer` (up to 180). `tone`: `own` (like the user's own sent emails), `formal` or `playful`. `picks`: the most Spilch picks in one reply, 1 to 3. `own_link`: add one of the user's own links when it fits the sender. `wink`: one light, kind line when the email is clearly a mass campaign. Anything else the user asks for ("warmer", "never say unfortunately", "always in Spanish") goes in `style.notes` as a short list of their own words. No `style`: use the standard.
- `links_pending`: true while any of the user's links is still in review, so the next run checks and tells them when one goes live.
- `history`: one entry per answered thread. `thread` is the mail thread's id, `drafted` is the full date and time the draft was written, and `shown` turns true once the user has seen it in a list or summary. Add `brand` so "redo Codeloom" can find it, unless `sharing` is `minimal`: then leave `brand` out and find the reply by its number in the last list or among the drafts labelled `Spilch`. Keep the last 100 entries. When you change `history`, send the whole list.
- `last_run`: the full date and time of the last run.

Write times as full timestamps (`2026-11-24T10:12:00Z`), never a date alone: "24 hours later" is measured from them.

Settings never hold email text, people's names or email addresses; Spilch refuses a save that contains an address.

## Coming from an older Spilch

Older versions kept settings in a mail draft with the subject `Spilch settings (keep this draft)`. If one exists and the account's settings have no `last_run`:

1. Read the newest such draft.
2. Save its `voice`, `style`, `history` and `last_run` with `spilch_settings`. Give each history entry a `thread` id if you can find its draft; turn a date-only `drafted` into that date at 00:00. Don't copy `send`, `sharing`, `spilch_line` or `daily_run`: the user chose those at sign-in. Don't copy `uid`, `email` or `links`.
3. Tell the user once: "I moved your Spilch settings to your account. You can delete the draft called *Spilch settings (keep this draft)*."

## Without the Spilch connector

There is nowhere to keep settings. Write replies as drafts only, send nothing, and say once that connecting Spilch keeps settings and adds picks from the network.
