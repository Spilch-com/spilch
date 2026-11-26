# Settings

Settings live on the user's Spilch account, so every chat, assistant and scheduled run reads the same ones. Read them with `spilch_settings` (no arguments) and change them with `spilch_settings`, action `set`, passing only the keys that change. A key set to `null` is removed.

```json
{
  "send": "ask",
  "send_since": "2026-11-24T13:05:20Z",
  "check": { "every": "off", "day": "mon", "time": "09:00" },
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

## The user's choices

Nothing is asked at sign-in. Each of these starts at its default, and the user changes it in chat. Don't open with a list of questions: change one when the user asks, and confirm in one line. The only thing you offer unasked is the weekly check, once.

- `send` (default `ask`): `ask` (each reply is saved as a draft and shown to the user; send only the ones they tell you to send, after they have seen them; nothing goes on a timer) or `drafts` (nothing is sent; the user sends from their mail). Never ask about it: show the drafts and ask which to send. A user who wants drafts only says so.
- `check` (default off): a regular check. `every` is `week`, `day` or `off`; `day` is `mon` to `sun` (used when weekly); `time` is a 24-hour time. Offer it once, after the first run: "Want a weekly check? Which day suits you? Once a week is plenty." Section `check` says how to schedule it.
- `sharing` (default `rich`): what Spilch learns about the companies that pitch: `rich` (Company profile), `facts` (Name and pitch) or `minimal` (Nothing). Never email text, people's names or addresses, whichever it is.
- `spilch_line` (default on): the `Sent with /spilch` signature line.

`send_since` and `configured` are kept by Spilch: `send_since` is the moment `send` last changed (only drafts written after it are sent), and `configured` is false until anything has been saved for the account, which tells you the user has chosen nothing yet. Don't set either.

## Kept by you between runs

- `voice`: greeting, sign-off and formality, read from the user's own sent mail.
- `style`: the reply style; the values above are the standard. `length`: `short` (3 to 4 sentences, 40 to 70 words), `normal` (60 to 120 words) or `longer` (up to 180). `tone`: `own` (like the user's own sent emails), `formal` or `playful`. `picks`: the most Spilch picks in one reply, 1 to 3. `own_link`: add one of the user's own links when it fits the sender. `wink`: one light, kind line when the email is clearly a mass campaign. Anything else the user asks for ("warmer", "never say unfortunately", "always in Spanish") goes in `style.notes` as a short list of their own words. No `style`: use the standard.
- `links_pending`: true while any of the user's links is still in review, so the next run checks and tells them when one goes live.
- `history`: one entry per answered thread. `thread` is the mail thread's id, `drafted` is the full date and time the draft was written, and `shown` turns true once the user has seen it in a list or summary. Add `brand` so "redo Codeloom" can find it, unless `sharing` is `minimal`: then leave `brand` out and find the reply by its number in the last list or among the drafts labelled `Spilch`. Keep the last 100 entries. When you change `history`, send the whole list.
- `last_run`: the full date and time of the last run.

Write times as full timestamps (`2026-11-24T10:12:00Z`), never a date alone.

Settings never hold email text, people's names or email addresses; Spilch refuses a save that contains an address.

## Coming from an older Spilch

Older versions kept settings in a mail draft with the subject `Spilch settings (keep this draft)`. If one exists and the account's settings have no `last_run`:

1. Read the newest such draft.
2. Save its `voice`, `style`, `history` and `last_run` with `spilch_settings`. Give each history entry a `thread` id if you can find its draft; turn a date-only `drafted` into that date at 00:00. Don't copy `send`, `sharing`, `spilch_line` or any schedule: those now live on the account. Don't copy `uid`, `email` or `links`.
3. Tell the user once: "I moved your Spilch settings to your account. You can delete the draft called *Spilch settings (keep this draft)*."

## Without the Spilch connector

There is nowhere to keep settings. Write replies as drafts only, send nothing, and say once that connecting Spilch keeps settings and adds picks from the network.
