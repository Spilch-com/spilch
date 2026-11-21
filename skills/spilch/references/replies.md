# Writing replies

For each picked or labelled email:

1. Read the thread. If it turns out personal, from someone the user knows, or already answered, skip it and say so in a few words.
2. Pick one or two recommendations (rules below). Three only when each clearly helps. With the Spilch connector, look at the user's vouches first (`spilch_vouch` with `action: "list"`) and prefer one when it fits the sender.
3. With the Spilch connector, call `spilch_create_link` for each link (uid, url, a short label like "seo agency"; never names or addresses) and use the `short_url`, so clicks can be counted.
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
- something the user vouched for;
- the user's own link from the settings, only when it truly fits this sender.

Niche beats famous: one sharp, specific pick is better than a household brand.

Always at least one. If nothing specific fits, a well-known free resource for their field.

**Real and checked.** Every link must exist. Find it with web search and open it with web fetch when you can; use the canonical page. Never invent a URL, title, author, statistic or discount. If you can't check links, recommend only widely known tools and publications by their homepage.

**On merit only.** No affiliate links, paid placements, discount codes or anything someone paid for. Never claim the user has used, read or loves something. No fake urgency. Don't recommend the sender's direct competitor as a dig.

**Off limits.** Nothing medical, legal, investment or political; no gambling, adult, crypto tokens, weapons or anything illegal; no personal information about private people. Never reply to scams, phishing or rude spam.

## Redo a reply

"Spilch it again", "Spilch this again", "another one", "different pick", "shorter", or any change asked about a Spilch draft: rewrite that reply. This is the one case where a brand already in `history` gets a new draft.
- Which one: the email the user names or has open; otherwise the last draft you wrote in this chat. Unsure: ask with the sender names as tappable choices.
- Already sent? Say "That one went out on <day>." and stop. Never send a second reply.
- Write a fresh version: follow what they asked; if they asked nothing specific, change the wording and pick different recommendations.
- Save it as the new draft in the same thread, then delete the old draft if the tools allow. If they don't, say "New version saved; delete the older draft in Gmail."
- Keep the 24-hour clock from the first draft, unless the user says "send now".
- Show the new reply text and nothing else.
