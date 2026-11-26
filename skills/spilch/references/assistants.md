# Notes per assistant

Tool names and abilities differ. Use what the assistant actually has; when a step needs something missing, give the user the one manual action.

## Claude (claude.ai, desktop, mobile)

- Gmail: search threads, read a thread, create a draft (prefer the HTML body), list and create labels, label threads. Sending may need the user's approval; ask once per batch.
- Reply-style choices: use the tappable-choices tool if offered.
- A regular check: create a scheduled task with the prompt in `references/check.md`.
- The longer check can be shown as an inline visual or an artifact with a ticked list.

## Claude Code and Cowork

- Gmail tools come from a connected Gmail connector; if none is connected, ask the user to connect one.
- Nothing is asked at sign-in. Settings start at their defaults and are changed in chat (`references/settings.md`).

## ChatGPT and other assistants

- Some mail connectors can read but not write drafts. Then show each reply as text with the thread's subject so the user can paste it, and say once: "Your mail connector can't save drafts here, so copy these into Gmail."
- If there's no scheduler, the user says *Spilch* to run the check. Once a week is plenty.
- The Spilch connector works anywhere that accepts a remote MCP server URL: https://spilch.com/mcp. The assistant opens Spilch's sign-in page when it is added. A chat that was already open cannot see the connector: the user starts a new chat and says *Spilch*.
