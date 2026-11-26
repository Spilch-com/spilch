# Inbox check

## What counts as a pitch

A first-contact email from someone the user hasn't written to, selling or proposing something: agencies (SEO, dev, design, marketing, lead-gen), software, link building, guest posts, outsourcing, recruiters offering candidates, sponsorships, partnerships, investor or broker outreach. Follow-ups on the same pitch count once; note how many emails they sent (`repeat`).

## What to skip

Anything personal; clients, colleagues and existing vendors; threads the user already replied to; automated mail (receipts, notifications, `noreply`, newsletters the user subscribed to); job applications to the user's own roles; legal, medical, financial or government mail. Never answer or list scams, phishing or fake invoices. When unsure, leave it out: a missed pitch costs nothing, a reply to a client costs a lot.

## Fit

- `strong`: a real business pitching something specific. Draft-worthy.
- `maybe`: thin, very early or unclear. List it, don't draft unless picked.
- `skip`: mass blast, irrelevant. Leave it out.

## The longer check

When the user asks for more ("look back 90 days", "full check"): search `in:inbox newer_than:90d -from:me -category:social` and `category:promotions newer_than:90d`, sample up to about 60 candidates, group them into 3 to 6 plain categories named by what the senders sell ("White-label dev", "SEO audits", "Recruiters"), and show a numbered list per category: `Brand: what they sell (date)`, strong fits first. Add one headline of at most 8 words about the pattern ("Mostly dev shops selling to agencies"). If you can show an inline visual or artifact, a ticked list there is nicer; never put email bodies or addresses in it. Then "Reply with the numbers to answer, or *all*."

## Pitch facts (the `sharing` setting)

With the Spilch connector, after the drafts are written, call `spilch_log_pitches` once with the candidates from this run and `sharing` set from the settings. This is only about the companies; sent replies and mentions are counted separately with `spilch_sent` (`references/check.md`). If your own permission check declines this call, skip it and carry on: it never blocks a reply.

- `rich` (default, "Company profile"): `brand`, `domain` (company domains only; leave it out for gmail.com, outlook.com and other free mail), `category`, `topics` (1 to 3), `pitch` (what they sell, one line), `replied` (true for every pitch that got a reply), plus `summary` (what the company does), `industry`, `company_size` (only if the email or their site states it), `need` (what they seem to be after, such as "more SaaS clients") and `repeat_count`.
- `facts` ("Name and pitch"): the first six fields only.
- `minimal` ("Nothing"): call it with `sharing: "minimal"` and one item per reply written, `{ "brand": "-", "replied": true }`. Nothing about the companies is stored. A short description of each company still goes to `spilch_find_pick` so it can choose a pick; it is used for the match and not kept.

Facts are about companies, never people: no names, email addresses, phone numbers or email text, in any field. When the sender is one person trading under their own name (a freelancer, a consultant, a personal domain), log only `category`, `topics` and `replied`, with `brand` as "-" and no `domain`, `summary` or `need`. If a fact isn't clear from the email or the company's public site, leave it out rather than guess.
