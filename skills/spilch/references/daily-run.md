# Daily run, "Spilch" and "Spilch it"

1. Read the newest settings draft.
2. Draft replies for emails the user labelled `Spilch` themselves: labelled threads with no Spilch draft, no reply from the user, and a brand not in `history`. A deleted draft means the user cancelled it; leave it. With `send: now`, send each right after writing it.
3. Check new pitches since `last_run` (`inbox-check.md`).
   - Draft right away for new `strong` fits and list them in the summary; list `maybe` ones without drafting. Drafts Spilch wrote on its own are never sent until the user has seen them listed in a summary (record `shown` in `history`).
   - `send` is `drafts`: these stay drafts, as always.
4. Due drafts: drafts in threads labelled `Spilch` whose brand is in `history` with a `drafted` date more than 24 hours ago, and drafted after the current `send` choice was set.
   - `send` is `24h` or `now` and you have a send tool: send only drafts the user picked, labelled, or was shown in an earlier summary. Re-read each thread first and skip any where the sender or the user wrote since, or the draft was deleted or emptied. If sending needs approval, ask once for the batch; in a scheduled run with nobody there, list them instead.
   - Otherwise list them: "2 drafts are ready in Gmail; press send when you like."
5. Log pitch facts at the `sharing` level (`inbox-check.md`).
6. Summary in the shape from `summaries.md`, three lines at most, plus the save nudge from `account.md` when it applies. Then update `last_run` and `history`.

Never send a reply before it has waited 24 hours as a draft, unless the user says "send now", or chose `send: now` and picked or labelled that email themselves. "Stop [name]" or deleting a draft cancels it.

## Scheduled task

If the user turns the morning check on and the assistant can schedule tasks, create one at the chosen time (default 09:00 local) with this prompt:

```
Run Spilch's daily run with the Spilch skill: read my "Spilch settings (keep this draft)" draft in Gmail, check new cold pitches since the last run, draft replies following my settings, handle drafts older than 24 hours by my sending setting, and give me the short summary.
```

If it can't schedule, say once: "Say *Spilch* any morning and I'll do the same check."
