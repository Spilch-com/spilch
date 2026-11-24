# Daily run and "Spilch now"

1. Read the settings with `spilch_settings`. If `links_pending` is true, call `spilch_links` with `list` once: name any link that is now live in the summary, and set `links_pending` to false when none is left in review.
2. Draft replies for emails the user labelled `Spilch` themselves: labelled threads with no Spilch draft, no reply from the user, and not in `history`. A deleted draft means the user cancelled it; leave it. With `send: now`, send each right after writing it.
3. Check new pitches since `last_run` (`inbox-check.md`).
   - Draft right away for new `strong` fits and list them in the summary; list `maybe` ones without drafting. Drafts Spilch wrote on its own are never sent until the user has seen them listed in a summary (record `shown` in `history`).
   - `send` is `drafts`: these stay drafts, as always.
4. Due drafts: drafts in threads labelled `Spilch` that are in `history` with a `drafted` time more than 24 hours ago and later than `send_since`. An entry with only a date counts from the end of that day.
   - `send` is `24h` or `now` and you have a send tool: send only drafts the user picked, labelled, or was shown in an earlier summary. Re-read each thread first and skip any where the sender or the user wrote since, or the draft was deleted or emptied. If sending needs approval, ask once for the batch; in a scheduled run with nobody there, list them instead.
   - Otherwise list them: "2 drafts are ready in Gmail; press send when you like."
5. Log pitch facts at the `sharing` level (`inbox-check.md`).
6. Summary in the shape from `summaries.md`, three lines at most. Then save `last_run` and `history` with `spilch_settings`.

Never send a reply before it has waited 24 hours as a draft, unless the user says "send now", or chose `send: now` and picked or labelled that email themselves. "Stop [name]" or deleting a draft cancels it.

## Scheduled task

If the user turns the morning check on and the assistant can schedule tasks, create one at the chosen time (default 09:00 local) with this prompt:

```
Run Spilch's daily run with the Spilch skill: read my Spilch settings, check new cold pitches since the last run, draft replies following my settings, handle drafts older than 24 hours by my sending setting, and give me the short summary.
```

If it can't schedule, say once: "Say *Spilch* any morning and I'll do the same check."

In a scheduled run where the Spilch connector isn't signed in or the settings can't be read, say Spilch needs connecting again and stop. Never fall back to defaults in a run nobody is watching.
