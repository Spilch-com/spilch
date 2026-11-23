# Spilch

Answer cold pitches instead of deleting them.

Spilch looks through your Gmail for first-contact pitches (agencies, tools, link building, recruiters, partnership offers), writes a short, kind no in your own voice, and adds something that genuinely helps the sender. When it fits, that is a link from someone else on Spilch; your own links (up to 3, free) travel in other people's replies the same way. Reply more, get recommended more. Each reply is saved as a draft in the same thread, labelled Spilch. You decide when anything is sent.

## Use it

1. Add the plugin from the Claude directory, or in Claude Code run `/plugin install spilch --marketplace Spilch-com/spilch`. Connect Gmail in your assistant's connectors.
2. Connect the Spilch connector from the plugin's **Connectors** tab. It carries the network: picks from other people, your links, mentions and click counts. Without it Spilch still writes replies, with no network pick.
3. Say **Spilch**. Within a minute you get your first real draft, a list of other recent pitches, and four quick choices: when replies go out (drafts only, after 24 hours, or right away for the ones you pick), a morning check, how much Spilch learns about the companies that pitch you, and whether replies end with "Sent with /spilch". Then it asks which links of yours (up to 3) other people's replies should recommend; new links are reviewed before they go live. Spilch never sends a reply you haven't seen listed.

After that, say **Spilch** any time, label an email `Spilch` in Gmail, or turn on the morning check. Change anything by chat: "send after 24 hours", "shorter replies", "no signature", "share nothing", "add a link", "how are my links doing?".

## What it does with your data

- **Your mail stays in your mailbox.** Spilch reads and writes mail only through your assistant's own Gmail connector. Your settings are a draft in your Gmail called "Spilch settings (keep this draft)".
- **The Spilch connector (spilch.com/mcp/core) never receives email text, people's names or email addresses.** It stores an anonymous id, the links you add for the network (up to 3: a link, a short name and who it helps), how often they were used in other people's replies and clicked, how many replies you wrote, the short links in your replies with their click counts, and facts about the companies that pitched you, at the level you choose:
  - *Company details* (default): brand, company domain, category, topics, a one-line description of the pitch, whether you replied, a short company summary, industry, rough size, what they seem to need, and how often they pitched you.
  - *Basic facts*: brand, company domain, category, topics, the one-line pitch and whether you replied.
  - *Nothing*: no pitch facts are sent.
- Short links (spilch.com/r/…) redirect to the page you recommended and count the click; the server keeps the time and country of the click, nothing about who clicked.
- These facts are descriptions your assistant writes about companies; they feed your weekly numbers (such as which kinds of companies pitch you most) and Spilch's aggregate statistics.
- To delete everything stored under your id, ask your assistant to "delete my Spilch data".
- If you keep the "Sent with /spilch" line on, replies end with it, linking to spilch.com. Say "no signature" to drop it.
- The network is anonymous: a sender sees a recommendation, never who added it. Mentions are earned by replying, not bought.
- About 1 in 10 picks comes from the Spilch team, and some of those pay us a commission. That funds Spilch. They follow the same rule as every pick: it fits the sender, or it is left out.

Privacy policy: https://spilch.com/privacy · Terms: https://spilch.com/terms · Support: i@asder.xyz

## Files

- `skills/spilch/SKILL.md` and `skills/spilch/references/`: the Spilch playbook.
- `.mcp.json`: the Spilch connector, https://spilch.com/mcp/core.

Made by Asder S.R.L. MIT licence.
