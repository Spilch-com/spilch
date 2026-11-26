# The check: every "Spilch" after the first

One check covers everything since the last one. Once a week is plenty for most people; the user can also just say *Spilch* whenever they like.

1. Read the settings with `spilch_settings`. If `links_pending` is true, call `spilch_links` with `list` once: name any link that is now live in the summary, and set `links_pending` to false when none is left in review.
2. Draft replies for emails the user labelled `Spilch` themselves: labelled threads with no Spilch draft, no reply from the user, and not in `history`. A deleted draft means the user cancelled it; leave it.
3. Check new pitches since `last_run` (`references/inbox-check.md`). Draft right away for new `strong` fits; list `maybe` ones without drafting.
4. Show what is waiting, in the list shape from the first run: every draft not yet sent, new ones first, each with what it recommends. Mark each as `shown` in `history`.
   - `send` is `ask`: ask which to send ("Send all, or the numbers?"). Send only the ones the user names, and only after they have seen them listed. Re-read each thread first and skip any where the sender or the user wrote since, or the draft was deleted or emptied. If sending needs approval, ask once for the batch.
   - `send` is `drafts`: send nothing. "3 drafts are ready in Gmail; press send when you like."
5. Count what was sent. Look in the user's Sent mail for the Spilch replies that really went out since the last check (a draft is not a sent reply), and count only those. Then call `spilch_sent` once with `replies` (how many) and `links` (the links from `spilch_find_pick` that were in them, exactly as given), so the people recommended get their mention. It takes a number and short links only. A draft that was never sent counts for nothing. Do the same right after sending replies in any other run.
6. Log pitch facts at the `sharing` level (`references/inbox-check.md`).
7. Summary in the shape from `references/summaries.md`, three lines at most. Then save `last_run` and `history` with `spilch_settings`.

Nothing is ever sent on a timer. A reply goes only when the user tells you to send it after seeing it, or when they press send in their mail. "Stop [name]" or deleting a draft cancels it.

## A regular check

After the first run, or when the user asks ("check every Monday", "every morning at 8", "stop the checks"), save it in `check` (`references/settings.md`) and confirm in one line.

If the assistant can schedule tasks, create one for the day the user chose, at 09:00 local unless they gave a time with this prompt:

```
Run Spilch's check: read my Spilch settings, look for new cold pitches since the last check, draft replies following my settings, list the drafts that are waiting, and give me the short summary. Send nothing.
```

If it can't schedule, say once: "Say *Spilch* whenever you like, once a week is plenty."

A scheduled check runs with nobody watching: it drafts and lists, and never sends. If the Spilch connector isn't signed in or the settings can't be read, say Spilch needs connecting again and stop. Never fall back to defaults in a run nobody is watching.
