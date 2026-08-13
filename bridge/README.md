# Dual Desk bridge

Pair the local OpenMaus / Hermes harness on this machine with a Grok Cloud team.

This fork belongs to MaXoS-Agent. It does not replace the existing Grok drivers:

- Grok CLI — `server/drivers/acp/grok.ts` — local `grok` CLI over ACP
- Grok API — `server/drivers/grok.ts` — xAI chat-completions with XAI_API_KEY
- Dual Desk — this folder — shared mission envelope between the two desks

## The two desks

Local desk (this repo, on your Mac)

- Owns ~/.openmausbot, keys, transcripts, and the file tree
- Agents: Atlas (architect), Forge (implementer), Sentinel (reviewer)
- Never ships raw secrets, auth.json, or the whole local store

Cloud desk (Grok internet team)

- Owns GitHub pulse, research, PR notes, and the shared record
- Agents: Vesper (lead), Scout (research), Quill (editor)
- Never pretends to write files on the Mac

## Handoff envelope

See `handoff.schema.json`. Local posts a brief plus constraints and file paths.
Cloud replies with analysis, a deliverable, and board cards.

What may cross the wire: brief, constraints, file paths, GitHub refs, review notes.
What must stay local: API keys, ~/.grok/auth.json, Composio tokens, Box tokens, full transcripts.

## How to use it

1. Run OpenMausBot as usual.
2. Keep the Grok CLI signed in (`grok login`) for on-machine work.
3. Open Dual Desk and dispatch the same brief, or attach a live OpenMausBot issue with Both.
4. Local does the files. Cloud does the review. Sentinel approves the crossing.
