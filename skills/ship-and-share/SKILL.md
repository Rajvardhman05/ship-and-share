---
name: ship-and-share
description: Draft social posts (X, LinkedIn) from real work done in a coding session, for someone building in public. Load when the user says "share this" (convert it into drafts, no judging), when they say "let's share this" or ask "should we share this?" (run the postworthy test first, draft only on a yes), AND at the end of any session where something postworthy happened so the session can suggest it. Carries the postworthy test, the hard filters, per-platform formats, and where drafts go.
---

# Ship and share

You ship all day and post nothing. The work already produces the material: findings, fixes, numbers,
reversals. This skill notices the good ones and turns them into drafts.

**The agent drafts. The human posts.** Never post, schedule, or open a social site on their behalf.

## Setup (first run)

Everything lives in one folder: `$SHIP_AND_SHARE_DIR` if set, otherwise `~/.ship-and-share/`.

- `voice.md` — who they are, what they are building, how they sound, what they never say.
- `queue.md` — the drafts. Newest at the top.
- `platforms.md` — which platforms they post on, and any per-platform notes.

If the folder or `voice.md` is missing, say so once, offer to create it from the templates in this
repo's `templates/` folder, and ask the three questions the voice file needs: what are you building,
who are you talking to, and what would you never say. Do not draft in a made-up voice.

## Three trigger points

**1. "Share this" — they have decided. Convert it.**
Do not judge whether it is postworthy; that call is theirs. Turn what they pointed at (or this session,
if they pointed at nothing) into 2–3 drafts with different angles. The hard filters still apply. If the
material is thin, say so in one line and still give the best honest angle.

**2. "Let's share this" / "should we share this?" — a wake-up call. Judge first.**
They are asking for a verdict. Run the postworthy test and answer plainly:
- **Yes** → one line on which criterion it clears, then 2–3 drafts.
- **No** → one or two lines on why not, and what would make it a post (the missing number, the proof,
  the incident). No drafts. Do not soften a no into a weak yes. Weak posts cost followers.
- **Not yet** → it could be a post once something is verified or measured. Say what.

**3. The session suggests.**
At the end of a session, run the same test on what happened. If it passes, write the drafts to the queue
and add ONE line to the final message:

> Worth sharing: 2 drafts in the queue. Best one: "<first ~12 words>…"

If it does not pass, say nothing. No "nothing to share today" line. Silence is the normal outcome and
most sessions end that way. Never interrupt work mid-session to suggest a post.

## The postworthy test

A post earns its place when a stranger who builds things would stop scrolling. It needs at least ONE of:

- **A surprise.** The cause was not what anyone would guess.
- **A real number with a before and after.** Measured, not estimated.
- **A changed mind.** They believed X, the evidence said Y, the plan changed.
- **A hard problem actually solved,** where the path is the interesting part, not the fact of fixing it.
- **A visible thing.** A feature, clip, or screen a person can look at and get in two seconds.
- **A useful comparison or alternative found** through real testing, with a concrete reason.
- **A principle that came out of a real incident,** stated with the incident attached.
- **An honest failure.** Something that did not work, and what it taught. These often do best.

And it must pass ALL of:

- **True and verified** in this session or the project's history. Only reasoned about is not a post.
- **Explainable in one breath** to someone who has never seen the codebase.
- **About the work, not about being busy.** "Shipped 6 PRs today" is not a post.

## Not postworthy

- Routine work: copy tweaks, dependency bumps, refactors, renames, config, CSS nudges.
- A merge, deploy, or PR count on its own. Activity is not a story.
- Anything where the honest version is "it works now" with no why.
- Plans, intentions, roadmaps, "excited to announce". Post what happened, not what might.
- Inside-baseball that needs three sentences of setup about the project's own file layout.
- The same insight as a draft already in the queue or posted in the last two weeks. Check the queue.
- Generic takes with no incident behind them. If it could be written without doing the work, skip it.

When unsure, skip. One strong post a week beats one weak post a day.

## Hard filters — never, even if asked in a hurry (say why, offer the safe version)

- **No content from real people's private data:** user conversations, customer records, support tickets,
  names, emails. Use synthetic or authored examples, and say so if context could imply a real user.
- **No secrets or internals that help an attacker:** keys, tokens, account or database ids, unpatched
  vulnerabilities, auth or payment bypass details.
- **No invented or rounded-up numbers.** No user counts, revenue, or growth claims that are not real
  and current. Never imply traction that is not there.
- **No claims the product cannot keep today.**
- **Nothing under NDA or belonging to an employer or client** unless `voice.md` says it is cleared.
- **No dunking on a competitor, vendor, or person.** Compare tools on facts, kindly.
- Anything in the "Never" list of `voice.md`.

## How to draft

1. Read `voice.md` and `platforms.md`. Do not draft from memory.
2. Read `queue.md` to avoid duplicates.
3. Write it the way they would tell one builder friend: what they expected, what happened, the number,
   what it means. Lead with the tension, not the setup. No hook formulas, no "here's what I learned",
   no thread emoji, no engagement bait.
4. Shape one finding per platform they use:
   - **X:** a single post under 280 characters, links counted as 23. Count it. A thread of 4–6 only for
     a real story with a turn in it, and each post must stand alone. Zero or one hashtag.
   - **LinkedIn:** 80–200 words. The first two lines must carry the whole point, because everything
     after them is hidden behind "see more". Short paragraphs, plain words, the same number and the
     same proof. It is not a longer tweet: give the context a non-specialist needs, and end on what
     changed, not on a question fishing for comments. No hashtag walls; zero to three.
   - **Anything else** listed in `platforms.md`: follow the limits and notes written there.
5. When they trigger it: 2–3 angles (the number, the story, the principle). When the session suggests:
   1–2 drafts, best first.
6. Every draft gets a **Proof** line: the exact screenshot, clip, chart, or before/after to attach, and
   where it lives. Posts with proof travel; claims do not. If the proof would break a hard filter, name
   a safe alternative.

## Where drafts go

Prepend to `queue.md`, under the first `---` line, newest first:

```
### YYYY-MM-DD — short title · angle · draft
**X:** the text, ready to paste
**LinkedIn:** the text, ready to paste
**Proof:** what to attach and where it is
**Source:** session / PR / commit it came from
```

Include only the platforms they use. Also show the drafts in chat when they triggered it. When the
session suggested, show only the one-line pointer.

Never rewrite or delete their status marks (`posted`, `skip`). If the folder is not reachable (a cloud
or sandboxed agent), show the drafts in chat, say the queue was not written, and never write drafts
into the project repository.
