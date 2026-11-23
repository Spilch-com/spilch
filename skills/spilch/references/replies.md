# Writing replies

For each picked or labelled email:

1. Read the thread. If it turns out personal, from someone the user knows, or already answered, skip it and say so in a few words.
2. **Network pick first.** With the Spilch connector, call `spilch_find_pick` with the uid and 2 to 5 topics about what the sender does or sells ("seo", "agencies"); never names, addresses or email text. If a pick truly helps this sender, call `spilch_create_link` with the uid and its `pick_id` and use the `short_url`; that counts the mention for whoever added it. Use every pick that truly helps this sender: one or two is usual, three at most, and never one that doesn't fit. No pick, or none that fits: go on without one.
3. You may add one recommendation of your own (rules below), or use it alone when there was no pick. For those, call `spilch_create_link` with the url and a short label like "seo agency", so clicks can be counted.
4. Save the reply as a **draft reply in the same thread** and apply the `Spilch` label if the tools allow. Add the brand to `history` in the settings with today's date as `drafted`.

## Shape of a reply

60 to 120 words before the signature; paragraphs and links only.

- Greeting with the first name ("Hi Dana,"), or "Hi," if you don't have it.
- One line that shows you read their email, naming what they offered.
- A short, friendly no or not-now. Never invent a reason; "not right now" is enough.
- The recommendations in one or two natural sentences tied to the sender, like a peer passing on something useful. Not a list, not a sales pitch.
- **Links sit inside the words**: link the name itself and save the draft with an HTML body where the tool allows (Gmail: `htmlBody`). Never write a bare URL in the text; Gmail rewrites them into long redirect lines. Put the page's own address in the link, and never copy a link back out of a draft you read. Plain-text tools only: the name alone for well-known things, at most one short bare address.
- The user's own sign-off.
- Signature line, only when `spilch_line` is on: `Sent with /spilch`, with `/spilch` linked straight to https://spilch.com (plain text: `Sent with /spilch · spilch.com`). Not a short link.
- Older than two weeks: open with "Catching up on my inbox:".
- Match the sender's language.

Example:

```
Hi Dana,

Thanks for the note about white-label builds for agencies. We're set on dev for now. Since you sell to agencies, <a href="https://spilch.com/r/abc1234">Agency Growth Weekly</a> is worth following, and <a href="https://…">this year's agency pricing report</a> is the clearest picture I've seen of how agencies buy dev work.

Best,
Ion

Sent with <a href="https://spilch.com">/spilch</a>
```

## Recommendation rules

**For the sender, not the user.** Something that helps the business they're pitching:
- a tool or service they would plausibly need;
- a genuinely good, recent read, report or guide in their field (prefer the last 12 months);
- a well-known newsletter, podcast or community in their field (prefer publications over private individuals);

If nothing fits, a well-known free resource for their field, or nothing: a kind no on its own is fine.

**Network picks are anonymous.** Write them like any other recommendation. Never say or guess who added one, and never call it sponsored or a partner. The user's own link (from `spilch_links`, action `list`) can go in their own reply too, when it truly fits this sender: link it with `spilch_create_link` and its url. That is not a network mention; mentions come from other people's replies.

**Real and checked.** Every link must exist. Find it with web search and open it with web fetch when you can; use the canonical page. Never invent a URL, title, author, statistic or discount. If you can't check links, recommend only widely known tools and publications by their homepage.

**Your own recommendations: on merit only.** No affiliate links, discount codes or anything someone paid for. (Network picks come only from `spilch_find_pick`.) Never claim the user has used, read or loves something. No fake urgency. Don't recommend the sender's direct competitor as a dig.

**Off limits.** Nothing medical, legal, investment or political; no gambling, adult, crypto tokens, weapons or anything illegal; no personal information about private people. Never reply to scams, phishing or rude spam.
