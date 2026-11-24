# Writing replies

For each picked or labelled email:

1. Read the thread. If it turns out personal, from someone the user knows, or already answered, skip it and say so in a few words.
2. **Network picks first, in one call for the whole run.** With the Spilch connector, call `spilch_find_pick` once with a `senders` list, one entry per pitch you are answering: `ref` (your label), `kind` ("SEO agency"), `sells`, `sells_to`, `industry`, `needs` (what would help that company do its own work better) and a few `topics`. Take these from the email and, when one quick look is enough, the company's site: a fuller, truer description gets better picks. Companies only: never a person's name, an address or email text. Each pick comes back with a ready `short_url`. Use every pick that truly helps that sender: one or two is usual, three at most, and never one that doesn't fit. No picks: go on without one.
3. You may add one recommendation of your own (rules below), or use it alone when there was no pick. For those, call `spilch_create_link` with the url and a short label like "seo agency", so clicks can be counted.
4. Save the reply as a **draft reply in the same thread** and apply the `Spilch` label if the tools allow. Add the thread to `history` in the settings with the time now as `drafted` (`settings.md`).

When the drafts are written, call `spilch_log_pitches` once (`inbox-check.md`) with `used_picks`: the network short links you actually put in replies. That is what counts the mentions.

**Keep it fast.** Two Spilch calls per run: one `spilch_find_pick` for all senders, one `spilch_log_pitches` at the end. One quick look at a sender's site at most; don't research.

## Shape of a reply

Follow the user's reply style (`style` in `settings.md`): length, tone, how many picks, their own link, the wink, and any `style.notes`. The standard is short (3 to 4 sentences, 40 to 70 words before the signature), in the user's own tone, up to 2 picks, their own link when it fits. Paragraphs and links only. The style never changes the rules in this file: a kind no, no invented reasons, links inside the words, nothing about the sender sent to Spilch beyond the sharing choice.

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

**Network picks are anonymous.** Write them like any other recommendation. If a pick comes with an `offer` (a discount, a trial, a code), you may pass it on in the words given; never change or invent one. Never say or guess who added one, and never call it sponsored or a partner. The user's own link (from `spilch_links`, action `list`) can go in their own reply too, when it truly fits this sender: link it with `spilch_create_link` and its url. That is not a network mention; mentions come from other people's replies.

**Real and checked.** Every link must exist. Find it with web search and open it with web fetch when you can; use the canonical page. Never invent a URL, title, author, statistic or discount. If you can't check links, recommend only widely known tools and publications by their homepage.

**Your own recommendations: on merit only.** No affiliate links, discount codes or anything someone paid for. (Network picks come only from `spilch_find_pick`.) Never claim the user has used, read or loves something. No fake urgency. Don't recommend the sender's direct competitor as a dig.

**Off limits.** Nothing medical, legal, investment or political; no gambling, adult, crypto tokens, weapons or anything illegal; no personal information about private people. Never reply to scams, phishing or rude spam.
