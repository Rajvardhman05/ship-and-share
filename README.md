# ship-and-share

**Your coding agent tells you when the work is worth posting.**

I ship all day and post nothing. The work produces plenty worth sharing: a bug whose cause nobody
would guess, a number that moved, a plan I reversed. By the time I think about posting, the moment is
gone and the blank box wins.

So I gave my coding agent one more job. When we solve something a stranger would stop scrolling for,
it says so and drafts the post. Most days it says nothing. That's the feature.

It is an [Agent Skill](skills/ship-and-share/SKILL.md) in the open [`SKILL.md` format](https://agentskills.io),
so any coding agent that loads skills can pick it up: Claude Code, Codex, Gemini CLI, GitHub Copilot,
Cursor and others. There is also a [Cursor rule](cursor/ship-and-share.mdc) and an
[`AGENTS.md` snippet](AGENTS-snippet.md) for agents that don't. Plain markdown, no code, no API keys. **The agent drafts. You post.** It never posts for you.

## How you use it

| You say | It does |
|---|---|
| **"share this"** | You've decided. It converts what you pointed at into 2–3 drafts. No judging. |
| **"should we share this?"** | A wake-up call. It runs the postworthy test first. Drafts on a yes. On a no, it tells you why and what's missing. It is allowed to say no. |
| *(nothing)* | At the end of a session where something cleared the bar, it adds one line: `Worth sharing: 2 drafts in the queue.` Otherwise, silence. |

**The phrases are yours.** Those are the defaults. Say "make it a tweet", "tweet this bro" or
"post-worthy?" instead if that's how you talk: list your phrases in the always-on block
([step 3](#install)) and the agent uses them. You choose what converts, what asks for a verdict, and
what the agent says when it nudges you.

Every draft is shaped per platform (X and LinkedIn out of the box) and comes with a **Proof** line:
the exact screenshot, chart or before/after to attach. Posts with proof travel. Claims don't.

## The postworthy test

A post earns its place when a stranger who builds things would stop scrolling. It needs at least one:

- **A surprise.** The cause was not what anyone would guess.
- **A real number with a before and after.** Measured, not estimated.
- **A changed mind.** You believed X, the evidence said Y, the plan changed.
- **A hard problem actually solved,** where the path is the interesting part.
- **A visible thing.** Something a person can look at and get in two seconds.
- **A useful comparison** found through real testing.
- **A principle that came out of a real incident,** with the incident attached.
- **An honest failure,** and what it taught. These often do best.

And all of: true and verified · explainable in one breath · about the work, not about being busy.

### Not postworthy

Routine work. A merge or PR count on its own. "It works now" with no why. Plans, roadmaps, "excited
to announce". Inside-baseball. Repeats. Generic takes you could have written without doing the work.

**When unsure, it skips.** One strong post a week beats one weak post a day.

### Hard filters

It refuses, even when you're in a hurry: real people's private data, secrets and attacker-useful
internals, invented or rounded-up numbers, implied traction, claims the product can't keep, anything
under NDA, and dunking on people or competitors. Plus whatever you put in your own "Never" list.

## What comes out

Real drafts from the week I built this, working on an AI character product:

> Spent a week trying to stop my AI character from interviewing people. A question in 80% of her
> replies. The cause turned out to be my own rules telling her to "be interested". Deleted two rule
> blocks. 80% became 57%. The fix was subtraction.

> Same still, same model, two renders. One kept her face, one turned her into a stranger by second
> three. The only difference: I let the canvas default to landscape on a portrait photo. Match the
> frame to the picture.

## Install

**1. Your files** (voice, queue, platforms). They live outside your projects, so drafts never end up in a repo.

```bash
git clone https://github.com/Rajvardhman05/ship-and-share.git
mkdir -p ~/.ship-and-share && cp -n ship-and-share/templates/*.md ~/.ship-and-share/
```

Then fill in `~/.ship-and-share/voice.md`. Ten honest lines is enough. Or skip this and the agent will
ask you the three questions it needs on first run. To keep the files somewhere else, set
`SHIP_AND_SHARE_DIR`.

**2a. Claude Code**

```bash
mkdir -p ~/.claude/skills && cp -r ship-and-share/skills/ship-and-share ~/.claude/skills/
```

Then do step 3. Claude Code reads the same block from `~/.claude/CLAUDE.md`.

**2b. Cursor**

```bash
mkdir -p .cursor/rules && cp ship-and-share/cursor/ship-and-share.mdc .cursor/rules/
```

**2c. Any other agent that supports Agent Skills** (Codex, Gemini CLI, GitHub Copilot, and
[others](https://agentskills.io))

Copy the `skills/ship-and-share` folder into your agent's skills directory. The location differs per
agent, so check its docs. The skill file itself needs no changes.

**3. The always-on block: your phrases and the end-of-session nudge (all agents)**

A skill loads when something calls for it, and the agent only knows what calls for it from its
always-on instructions. So your trigger phrases and the end-of-session nudge live in one short block.
Paste [`AGENTS-snippet.md`](AGENTS-snippet.md) into your `AGENTS.md` (or `~/.claude/CLAUDE.md` for
Claude Code), then edit the three phrase lines to whatever you naturally say. In Cursor, edit the
"Your phrases" block at the top of the rule file instead.

**No skills support at all?** Paste the body of [`cursor/ship-and-share.mdc`](cursor/ship-and-share.mdc)
into your agent's instructions file. It is the whole thing in one page.

## Status

Built and used daily in Claude Code. The Cursor rule is the same rules in Cursor's format and is newer.
The skill follows the open Agent Skills format, so it should load anywhere that format is supported,
but I have only run it in Claude Code and Cursor. If you try it elsewhere, open an issue and tell me
how it went. If the bar feels too strict or too loose for you, edit the lists. They're yours.

## Why the bar is strict

An agent that suggests a post after every session is a notification you learn to ignore, and posting
what it drafts trains your followers to scroll past you. Silence is what makes the nudge mean
something.

MIT licensed. Built by [@Rajvardhman05](https://github.com/Rajvardhman05).
