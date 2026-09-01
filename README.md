# Anti-Slop Design

A restraint-first design and writing critique skill for coding agents. Give it a product surface — UI, a landing page, a dashboard, store art, charts, interface copy — and it names the concrete patterns that make the work feel generated, then makes the minimum effective changes to the real product instead of rebuilding a generic version of it.

It runs on any agent that loads the Agent Skills convention (`SKILL.md` plus reference files): Claude Code, Codex, ZCode, and others. The skill is plain markdown, so it also works as a standalone review checklist for a human.

## What it actually does

- **Three operating modes.** Create (ground, build, verify), critique (report the few highest-leverage findings, edit nothing), revise (audit, minimal changes, re-audit).
- **Four surface modes.** Persuade, operate, read, experience — chosen from the surface in front of the user, because a landing page, a dashboard, and documentation fail in different ways.
- **An eight-pass workflow.** Ground the artifact in its real content and tokens, separate evidence from judgment, commit to one direction, edit copy semantically, flatten decorative structure, spend visual emphasis deliberately, pass the accessibility gate, then implement and verify.
- **Observable patterns, not guesses.** It never claims "an AI made this." It names the pattern and its effect: card soup, synonym cycling, uniform cadence, importance puffery, unearned glow, stacked containers, invented claims.
- **Priorities with an order.** P0 truth and access failures before P1 hierarchy failures before P2 polish. No polishing decoration while the page's job is unclear.
- **It protects your product.** Established tokens and component contracts are normative, canonical assets get reused rather than imitated, and if the work is already distinctive it says so and stops instead of manufacturing a redesign.

## Install

Clone straight into your agent's skills directory:

```bash
# Claude Code
git clone https://github.com/thedevmark/anti-slop-design.git ~/.claude/skills/anti-slop-design

# Codex
git clone https://github.com/thedevmark/anti-slop-design.git ~/.codex/skills/anti-slop-design

# ZCode
git clone https://github.com/thedevmark/anti-slop-design.git ~/.zcode/skills/anti-slop-design
```

On Windows the same commands work in Git Bash; in PowerShell replace `~/` with your home directory. To share one copy across agents, clone once and symlink the others into it. For a single project only, clone into `.claude/skills/` (or your agent's project-level equivalent) inside the repo.

No skill infrastructure? Open `SKILL.md`, read it, and apply it. That is the whole mechanism.

## Use

Ask your agent, in plain language:

- "Use anti-slop-design to critique the pricing page."
- "Revise the empty states on the dashboard. Distill, don't redesign."
- "Audit this store screenshot set for slop before I ship it."

The skill also triggers on words like polish, hierarchy, taste, density, clarify, distill, harden, quieter, or bolder. For a critique it returns a verdict plus three to five findings with location, effect, and the exact correction. For a revision it reports what changed, what was preserved, and what was actually verified — it does not claim a render or a test that did not happen.

## Files

| file | job |
|---|---|
| `SKILL.md` | The skill itself: modes, workflow, priorities, completion gate |
| `references/writing-and-copy.md` | Copy rules, pattern-cluster table, editing tests, example corrections |
| `references/visual-and-interaction.md` | Visual tell catalog and verification matrix |
| `references/evidence-and-testing.md` | Evidence labeling and audit method |
| `references/promotional-assets-and-feedback.md` | Store art, thumbnails, social graphics, iterative feedback handling |
| `agents/openai.yaml` | Interface metadata for OpenAI-compatible agent hosts |

## Where this fits: context engineering

This skill is one public piece of a context-engineering system I am building across my repositories. The premise: you get better agent work by engineering what the agent sees than by writing a cleverer prompt. Each repo carries its own operating context — an `AGENTS.md` that is the single authority, thin tool adapters instead of duplicated instructions, a routing index that loads only task-relevant files on demand, guarded versioned memory for durable facts, compaction and sub-agent isolation conventions, and an executable test that fails when the context layer itself drifts. The repos prompt themselves; the agent arrives routed.

This repo is the shareable surface of that system: the skill that keeps the output honest while the context layer keeps the input honest. The private side is in active development and in daily use.

## License

MIT
