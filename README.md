# Spilch

Answer cold pitches instead of deleting them.

Spilch looks through your Gmail for first-contact pitches (agencies, tools, link building, recruiters, partnership offers), writes a short, kind no in your own voice, and adds one or two recommendations that genuinely help the sender: a tool they could use, a good read in their field, a community worth joining. Each reply is saved as a draft in the same thread, labelled Spilch. You decide when anything is sent.

## Use it

1. Add the plugin from the Claude directory, or in Claude Code run `/plugin install spilch --marketplace asder-x-y-z/spilch-plugin`. Connect Gmail in your assistant's connectors.
2. Optional: connect the Spilch connector from the plugin's **Connectors** tab, for short links with click counts and weekly numbers.
3. Say **Spilch**. Within a minute you get your first real draft, a list of other recent pitches, and four quick choices: when replies go out (drafts only, after 24 hours, or right away for the ones you pick), a morning check, how much Spilch learns about the companies that pitch you, and whether replies end with "Sent with /spilch". Spilch never sends a reply you haven't seen listed.

After that, say **Spilch** any time, label an email `Spilch` in Gmail, or turn on the morning check. Change anything by chat: "send after 24 hours", "shorter replies", "no signature", "share nothing".

## What it does with your data

- **Your mail stays in your mailbox.** Spilch reads and writes mail only through your assistant's own Gmail connector. Your settings are a draft in your Gmail called "Spilch settings (keep this draft)".
- **The Spilch connector (spilch.com/mcp/core) never receives email text, people's names or email addresses.** It stores an anonymous id, the links you recommend with their click counts, and facts about the companies that pitched you, at the level you choose:
  - *Company details* (default): brand, company domain, category, topics, a one-line description of the pitch, whether you replied, a short company summary, industry, rough size, what they seem to need, and how often they pitched you.
  - *Basic facts*: brand, company domain, category, topics, the one-line pitch and whether you replied.
  - *Nothing*: no pitch facts are sent.
- Short links (spilch.com/r/…) redirect to the page you recommended and count the click; the server keeps the time and country of the click, nothing about who clicked.
- These facts are descriptions your assistant writes about companies; they feed your weekly numbers (such as which kinds of companies pitch you most) and Spilch's aggregate statistics.
- To delete everything stored under your id, ask your assistant to "delete my Spilch data".
- If you keep the "Sent with /spilch" line on, replies end with it, linking to spilch.com. Say "no signature" to drop it.
- Recommendations are chosen on merit. Spilch carries no paid placements or affiliate links.

Privacy policy: https://spilch.com/privacy · Terms: https://spilch.com/terms · Support: i@asder.xyz

## Files

- `skills/spilch/SKILL.md` and `skills/spilch/references/`: the Spilch playbook.
- `.mcp.json`: the Spilch connector, https://spilch.com/mcp/core.

Made by Asder S.R.L. MIT licence.
