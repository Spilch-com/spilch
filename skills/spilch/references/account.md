# Saving the user's Spilch (linking their email)

Optional. Call it "saving your Spilch", never an account, a login or history. A linked email lets the user recover their Spilch (lost settings draft, another mailbox or another assistant) and gives their business a verified mark when the address is on its own domain. Needs the Spilch connector. Offer it once; never push.

1. One tappable-choices card: "Save your Spilch to <the mailbox address>? Your links, clicks and vouches stay yours if you change assistant or mailbox, and your business gets a verified mark": **Yes** / Not now; and "Updates from Spilch, a few a month": **No** / Yes.
2. On yes, call `spilch_link_email` with the uid, the address of the mailbox you are connected to (never another address) and `updates`.
3. Send the returned email exactly as given (from, to, subject, body). The user's yes in step 1 is the approval for this one email; never send it without that yes.
4. Wait about 30 seconds, then call `spilch_account`. `pending`: check once more a minute later; still pending, say "Sent. It'll show as linked shortly." `verified`: one line, "Saved. Your Spilch is linked to <email>."
5. If `primary_uid` differs from the uid, the user had Spilch before: write `primary_uid` into the settings draft as `uid` and say "Welcome back. Your earlier Spilch is restored." Set `email_linked: true` in the settings draft.

**Used Spilch before?** If there is no settings draft but `in:sent to:verify@spilch.com` finds an email, the user linked Spilch before: after the first drafts, offer this flow so their earlier vouches and numbers come back.

Spilch stores the address, its domain, when it was verified and the updates choice, nothing else from that email. "Delete my Spilch data" removes the link.

## When to offer it

- **End of the first run**, one line: "Your Spilch lives in a Gmail draft called *Spilch settings (keep this draft)*. Keep it: that's how every chat finds your Spilch." If the email isn't linked, add: "Say *save my Spilch* to keep it even if that draft goes."
- **Daily run**, as one extra line in the summary, only when `email_linked` isn't true, the user has at least one click or three vouches, `save_asked` is below 3 and `save_asked_at` is more than 14 days ago or empty: "Save your Spilch? Your <N> clicks and <M> vouches stay yours if you change assistant or mailbox. Say *save my Spilch*." Then add 1 to `save_asked` and set `save_asked_at` to today. "Don't ask again" sets `save_asked` to 3.
- "Save my Spilch" at any time starts the flow above.
