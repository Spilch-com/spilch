# Spilch

Answer cold pitches instead of deleting them.

Spilch looks through your Gmail for first-contact pitches (agencies, tools, link building, recruiters, partnership offers), writes a short, kind no in your own voice, and adds one or two recommendations that genuinely help the sender: a tool they could use, a good read in their field, a community worth joining, or something you or another Spilch user vouches for. Each reply is saved as a draft in the same thread, labelled Spilch. You decide when anything is sent.

## Use it

1. Add the plugin from the Claude directory, or in Claude Code run `/plugin install spilch --marketplace Spilch-com/spilch`. Connect Gmail in your assistant's connectors.
2. Optional: connect the Spilch connector from the plugin's **Connectors** tab, for short links with click counts and weekly numbers.
3. Say **Spilch**. Within a minute you get your first real draft, a list of other recent pitches, and four quick choices: when replies go out (drafts only, after 24 hours, or right away for the ones you pick), a morning check, how much Spilch learns about the companies that pitch you, and whether replies end with "Sent with /spilch". Spilch never sends a reply you haven't seen listed.

After that, say **Spilch** any time for new pitches and **Spilch it** to reply to the ones you pick, label an email `Spilch` in Gmail, or turn on the morning check.

Optional, with the Spilch connector:

- **Vouch.** Tell Spilch what you would recommend to a stranger: your business, a niche tool, someone worth following. Your assistant can suggest candidates from your website and inbox; you tick what you vouch for. Your own things can appear in other Spilch users' replies, with the name you choose.
- **Link your email.** Your assistant sends one short email from your mailbox to verify@spilch.com. Then you can recover your Spilch from another assistant or mailbox, and an address on your business domain gives it a verified mark. Change anything by chat: "send after 24 hours", "shorter replies", "no signature", "share nothing".

## What it does with your data

- **Your mail stays in your mailbox.** Spilch reads and writes mail only through your assistant's own Gmail connector. Your settings are a draft in your Gmail called "Spilch settings (keep this draft)".
- **The Spilch connector (spilch.com/mcp/core) never receives email text, or the names and addresses of people who wrote to you.** The only address it can get is your own, if you choose to link it. It stores an anonymous id, the links you recommend with their click counts, and facts about the companies that pitched you, at the level you choose:
  - *Company details* (default): brand, company domain, category, topics, a one-line description of the pitch, whether you replied, a short company summary, industry, rough size, what they seem to need, and how often they pitched you.
  - *Basic facts*: brand, company domain, category, topics, the one-line pitch and whether you replied.
  - *Nothing*: no pitch facts are sent.
- Short links (spilch.com/r/…) redirect to the page you recommended and count the click; the server keeps the time and country of the click, nothing about who clicked.
- These facts are descriptions your assistant writes about companies; they feed your weekly numbers (such as which kinds of companies pitch you most) and Spilch's aggregate statistics.
- **Vouches**: the links you chose to recommend, a short name, who they help and, for your own things, the public name you picked. The website scan reads a few public pages of the site you give and saves nothing until you tick.
- **Linked email (optional)**: your address, its domain, when it was verified and whether you want updates.
- To delete everything stored under your id, including vouches and a linked email, ask your assistant to "delete my Spilch data".
- If you keep the "Sent with /spilch" line on, replies end with it, linking to spilch.com. Say "no signature" to drop it.
- Recommendations are chosen on merit. Spilch carries no paid placements or affiliate links.

Privacy policy: https://spilch.com/privacy · Terms: https://spilch.com/terms · Support: i@asder.xyz

## Files

- `skills/spilch/SKILL.md` and `skills/spilch/references/`: the Spilch playbook.
- `.mcp.json`: the Spilch connector, https://spilch.com/mcp/core.

Made by Asder S.R.L. MIT licence.
