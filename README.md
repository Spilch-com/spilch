# Spilch

Answer cold pitches instead of deleting them.

Spilch looks through your Gmail for first-contact pitches (agencies, tools, link building, recruiters, partnership offers), writes a short, kind no in your own voice, and adds something that genuinely helps the sender. When it fits, that is a link from someone else on Spilch; your own links (up to 3, free) travel in other people's replies the same way. Reply more, get recommended more. Each reply is saved as a draft in the same thread, labelled Spilch. You decide when anything is sent.

## Use it

1. Add the plugin from the Claude directory, or in Claude Code run `/plugin marketplace add Spilch-com/spilch` and then `/plugin install spilch-replies@spilch`. Connect Gmail in your assistant's connectors.
2. Connect the Spilch connector from the plugin's **Connectors** tab. It opens Spilch's sign-in page: confirm your email with a 6-digit code (or Google), then pick four settings: when replies go out (after 24 hours by default, so you can edit or delete a draft first; drafts only; or right away for the ones you pick), a morning check, how much Spilch learns about the companies that pitch you, and whether replies end with "Sent with /spilch". Without the connector Spilch still writes replies, as drafts only and with no network pick.
3. Say **Spilch**. Within a minute you get a small dashboard of your last 14 days: how many cold pitches, what kinds, and your first real reply already drafted. Then it asks what other people's replies should recommend for you: up to 3 links, free (your business, an offer, a blog post, a how-to). Links are reviewed before they go live. Spilch never sends a reply you haven't seen listed.

After that, say **Spilch** any time, label an email `Spilch` in Gmail, or turn on the morning check. Change anything by chat: "send after 24 hours", "shorter replies", "no signature", "share nothing", "add a link", "how are my links doing?", "redo 2" (or name the company) to rewrite a reply, "reply style" to change how replies sound.

## What it does with your data

- **Your mail stays in your mailbox.** Spilch reads and writes mail only through your assistant's own Gmail connector.
- **The Spilch connector (spilch.com/mcp) never receives email text, people's names or anyone else's email address.** It stores:
  - your own email address, from sign-in, which is how Spilch knows your links are yours and where it writes when they go live;
  - your settings, and what your assistant keeps between runs: your greeting and sign-off, your reply style, and a list of the mail threads already answered (a thread id, when the draft was written and, unless you chose *Nothing* below, the company's name);
  - the links you add for the network (up to 3: a link, a short name, who it helps, its kind and an optional offer), how often they were used in other people's replies and clicked, how many replies you wrote, and the short links in your replies with their click counts;
  - facts about the companies that pitched you, at the level you choose:
    - *Company profile* (default): brand, company domain, category, topics, a one-line description of the pitch, whether you replied, a short company summary, industry, rough size, what they seem to need, and how often they pitched you.
    - *Name and pitch*: brand, company domain, category, topics, the one-line pitch and whether you replied.
    - *Nothing*: nothing about the companies is sent; only the number of replies you wrote is counted.
- Short links (spilch.com/r/…) redirect to the page you recommended and count the click; the server keeps the time and country of the click, nothing about who clicked.
- To find links that fit, your assistant also sends a short description of each company that pitched you (what it is, what it sells, who to, what would help it). It is used for matching and not stored.
- Spilch emails you only your sign-in code and a note when one of your links goes live, plus occasional news if you ticked that box.
- These facts are descriptions your assistant writes about companies; they feed your weekly numbers (such as which kinds of companies pitch you most) and Spilch's aggregate statistics.
- To delete your account and everything stored under it, ask your assistant to "delete my Spilch data".
- If you keep the "Sent with /spilch" line on, replies end with it, linking to spilch.com. Say "no signature" to drop it.
- The network is anonymous: a sender sees a recommendation, never who added it. Mentions are earned by replying, not bought.
- Some picks are added by the Spilch team to get the network started: plain links to well-known tools and resources. Nobody pays to be recommended, and there are no affiliate links. They follow the same rule as every pick: it fits the sender, or it is left out.

Privacy policy: https://spilch.com/privacy · Terms: https://spilch.com/terms · Support: i@asder.xyz

## Files

- `skills/spilch/SKILL.md` and `skills/spilch/references/`: the Spilch playbook.
- `.mcp.json`: the Spilch connector, https://spilch.com/mcp.

Made by Asder S.R.L. MIT licence.
