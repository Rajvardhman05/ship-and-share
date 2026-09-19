<!-- Paste this into your AGENTS.md (or your agent's always-on instructions file).
     It is the always-on half: it makes the agent suggest a post at the end of a good session.
     The full rules live in the skill; if your agent cannot load skills, paste
     cursor/ship-and-share.mdc (without its frontmatter) instead of this snippet. -->

## Ship and share

I build in public. The `ship-and-share` skill holds the rules; follow it whenever it applies.

- **"share this"** → I have decided. Convert it into 2–3 drafts, no judging.
- **"let's share this" / "should we share this?"** → run the postworthy test first. Draft only on a
  yes. On a no, tell me why and what is missing. You are allowed to say no.
- **End of session:** if something genuinely postworthy happened (a surprise, a real before/after
  number, a changed mind, a hard problem solved, a visible thing, an honest failure), queue the drafts
  and add ONE line to your closing message: `Worth sharing: 2 drafts in the queue.` If nothing clears
  the bar, say nothing. Never interrupt work mid-session to suggest a post.

You draft. I post. Never post or schedule on my behalf. Drafts go to `~/.ship-and-share/queue.md`
(or `$SHIP_AND_SHARE_DIR`), never into this repository.
