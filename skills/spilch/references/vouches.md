# Vouches

A vouch is something the user would recommend to a stranger themselves: their own business or link (`yours`), a tool (`tool`), a person or small business (`person`), or a read (`read`). Vouched links go into replies when they fit the sender. Needs the Spilch connector.

## Finding candidates

Offer both, then show everything in one multi-select tappable-choices card grouped Yours / Tools / People / Reads, niche first. Leave out anything marked `mass_market` unless nothing else is left.

- **Website.** Ask for it in one line if you don't know it, then call `spilch_scan_site` with the uid and the address. It reads a few public pages and returns suggestions; it saves nothing.
- **Inbox.** Search the last 12 months for receipts and invoices (`subject:(receipt OR invoice OR subscription OR "your order") newer_than:1y`), newsletters the user keeps reading, and small businesses they have written to more than twice. Keep products, newsletters and small businesses; skip big household brands, banks, utilities, government, health and anything personal. For each, find the public homepage yourself (never a link copied out of an email) and write a one-line `for_whom`. Never pass amounts, email text, email addresses or people's names; a business name is fine.

## Saving

Save the ticked ones with `spilch_vouch` (`action: "add"`, `source: "scan"` for scanned ones, a one-line `for_whom` each, up to 20 per call). Receipt in one line: "Vouched for 6. They'll show up in replies when they fit."

Typed by hand ("vouch for podpage.com, it's great for podcast sites"): add it the same way, no card needed.

## Managing

- "What do I vouch for?": `spilch_vouch` with `action: "list"`; show names one per line.
- "Remove …": `action: "remove"` with the ids from the list.

## In replies

List the user's vouches (`spilch_vouch`, `action: "list"`) once per run and pick from them by `for_whom`. Use one, at most two, and only when it truly fits the sender.
