# Intro to Applied AI Engineering

**A quickstart for using AI to think, document, and learn on work you actually care about.**

This is not a course. There's no clock, no grade, no toy exercises. It's a starter repo and a short, self-paced workshop that gets you doing real knowledge work with an AI agent in an afternoon. You open it, point an agent at it, and turn it into a living **LLM wiki**: a system that reads your source material, builds knowledge you can question, documents both the work *and* your own learning, and tells you whether it can be trusted.

## The big why

Most people use AI as an answer machine: ask, copy, forget. It feels productive and teaches you nothing — the fluency that makes a model sound smart is the same fluency that hides what you don't actually understand.

This repo is the alternative. You build a small **engine** that sits on top of your own material and helps you figure out what you don't yet know — while keeping *you* the critical thinker in the loop. The goal isn't answers faster. It's better thinking, documented as you go, that you can trust because you tested it.

That pattern works on anything knowledge-heavy: a codebase, a research area, a pile of docs, a decision you're stuck on, a topic you're trying to learn.

## How the wiki works

This repo already **is** a working LLM wiki. The structure, the rules, and the seed files are all in place — you don't scaffold anything. You add your material, point the agent at it, and start asking questions.

```text
   ┌─ AGENTS.md ── the schema · rules you own; the agent reads it first ─┐
   └──────────────────────────────────┬─────────────────────────────────┘
                                       ▼
   you ──drop raw material──▶  sources/  ──the agent reads──▶  agent (opencode)
                              (read-only)                           │
                                                                    │ writes
                                                                    ▼
   you ◀──read pages · ask grounded questions──  wiki/  (the knowledge base)

   the honesty loop:  ask ▶ wiki answers, with citations ▶ you check ▶ log it
                      ▶ add an eval ▶ tighten AGENTS.md ▶ repeat
```

Three layers, and **you own the boundary between them**:

- **[`sources/`](README.md)** — raw material you provide. The agent **reads** it; it never edits it.
- **[`wiki/`](wiki/index.md)** — the knowledge base the agent **writes**: an index, concept pages, source summaries, two logs, and an eval set.
- **[`AGENTS.md`](AGENTS.md)** — the **schema** that makes the agent behave like a disciplined librarian instead of a chatbot. When it misbehaves, you fix this file.

You stay responsible for purpose, judgment, standards, and acceptance. The agent does the legwork.

## Get started

**Start in the workshop.** Open [`workshop/00-orientation.md`](workshop/00-orientation.md) and work the modules in order. They're short and self-paced — do them in whatever session length you've got.

1. Read [`workshop/00-orientation.md`](workshop/00-orientation.md) — the lay of the land.
2. Set up your tools in [`workshop/02-setup.md`](workshop/02-setup.md) (see below).
3. Drop your own material into [`sources/`](README.md) and let the agent build [`wiki/`](wiki/index.md).

Do the hands-on steps on *your* material, not a sample. The whole point is to walk away with a wiki you keep using.

## Where your raw material goes

Everything the wiki is built from lives in **[`sources/`](README.md)** — specs, design docs, notes, data, articles, transcripts: anything the agent should reason *from*. Drop files straight into that folder. Three rules:

- **Read-only.** The agent reads these; it never changes them. If a source is wrong, the agent notes that *in the wiki* and leaves the source as-is — so you always know what the wiki was built on.
- **No secrets.** Never put credentials, keys, or private personal data here. Assume everything in this folder gets read in full.
- **Name files clearly.** Every wiki claim cites its source file, so `spec-v2.md` beats `doc1.md`.

## Using the wiki

Once your tools are set up (below) and material is in `sources/`:

1. **Ingest.** Ask the agent to read `sources/` — it summarizes each file, extracts the key concepts and entities into their own linked pages, cites every claim, and updates [`wiki/index.md`](wiki/index.md).
2. **Ask, grounded.** Ask questions it answers *from your sources*, with citations — e.g. *"Based only on the sources, what does the spec say about X, and what does it leave unspecified?"*
3. **Read.** Open [`wiki/index.md`](wiki/index.md) and follow the links; in Obsidian, use the graph view to see how pages connect. Anything marked `> Unverified:` or `> Inference:` isn't backed by a source — treat it with suspicion.
4. **Keep it honest.** Run the [eval set](wiki/evals.md), label any failures, and tighten [`AGENTS.md`](AGENTS.md). Your two logs grow as you go: the [project log](wiki/log.md) (what happened) and the [learning log](wiki/learning-log.md) (what *you* figured out).

**Learn from it, don't just query it.** The wiki is also a tutor. Ask the agent to *teach* you something from your sources — to run a Socratic dialogue, quiz you, or grade an explanation you attempt — instead of just handing you the answer. It's built to provoke your thinking and grade honestly (not flatter), then prompt you to capture what clicked in the [learning log](wiki/learning-log.md), in your own words. See module [05 · Learning with AI](workshop/05-learning-with-ai.md).

Module [03 · Document & Wiki](workshop/03-document-and-wiki.md) walks through all of this hands-on.

## Tools you'll use

You need three things. The workshop walks you through each in [`02-setup.md`](workshop/02-setup.md).

| Tool | Role | Notes |
|---|---|---|
| **[opencode](https://opencode.ai)** | The agent harness | Runs the agent: reads `sources/`, writes `wiki/`, follows `AGENTS.md` automatically. This is the engine. |
| **A provider key** | The model behind the agent | Use a capable reasoning model, and **set a hard spend cap before your first run.** |
| **[VS Code](https://code.visualstudio.com) and/or [Obsidian](https://obsidian.md)** | Your editor | How you read and browse the wiki. Pick by what fits your work. |

**VS Code vs. Obsidian** — both work; this is preference, not correctness:

- Use **VS Code** if your project is *code* or lives near a terminal and Git. It runs opencode inline and handles config and version control well.
- Use **Obsidian** if your project is *knowledge you want to navigate and connect* — it gives you beautiful Markdown, backlinks, and a graph view of how your wiki pages relate.
- Many people run **both**: VS Code for the agent and Git, Obsidian to read the wiki and see its shape.

## The steps you'll take

The workshop is six short modules. Each adds one piece of the engine.

| Module | What you do |
|---|---|
| [00 · Orientation](workshop/00-orientation.md) | See the whole picture and how the pieces fit. |
| [01 · Concepts](workshop/01-concepts.md) | The working vocabulary — tokens, context, agents, evals, the failure modes to hunt. |
| [02 · Setup](workshop/02-setup.md) | Get opencode, a model, and your editor working. |
| [03 · Document & Wiki](workshop/03-document-and-wiki.md) | Ingest your sources, build the wiki, start the two logs. **The core.** |
| [04 · Evaluation Loop](workshop/04-evaluation-loop.md) | Turn "I think it works" into "I tested it" — and fix what fails. |
| [05 · Learning with AI](workshop/05-learning-with-ai.md) | Use the model as a tutor that provokes your thinking, not one that replaces it. |
| [06 · Put It to Work](workshop/06-put-it-to-work.md) | Point the whole engine at a real problem of your own, end to end. |

## What you'll have at the end

- A working **LLM wiki** for your project: raw sources the agent reads, a knowledge base it maintains, and an `AGENTS.md` schema you've made your own.
- A **two-track documentation habit**: a project log of what happened, and a learning log of what *you* figured out.
- An **evaluation loop** you can run to check whether the wiki — and your own understanding — actually hold up.

## Repo map

| Path | What it is |
|---|---|
| [`workshop/`](workshop/) | Start here. The six modules, in order. |
| [`AGENTS.md`](AGENTS.md) | The schema. The rules the agent follows: how to maintain the wiki, document both tracks, log everything, and stay honest. Read it. |
| [`sources/`](README.md) | Raw, immutable inputs. The agent reads these; it never edits them. |
| [`wiki/`](wiki/index.md) | The agent-owned knowledge base: an index, two logs, an eval set, and concept pages. |
| [`decks/`](decks/README.md) | Slide decks — the visual companion to the concepts. Present from them or just read them. |
| [`RESOURCES.md`](RESOURCES.md) | Further reading and watching — the ideas this workshop is built on, with notes on how each connects. |

## The mantra

> Start small. Write it down. Verify before you trust.

## Further resources

Want to go deeper on the ideas behind this workshop? See [`RESOURCES.md`](RESOURCES.md) for a short, annotated list — Karpathy's LLM-wiki pattern, the evals discipline behind Module 04, and a few talks and books on staying the critical thinker in the loop.

---

Credit: the wiki pattern is Andrej Karpathy's *LLM Wiki*. The evaluation loop draws on Hamel Husain's error-analysis work. The ladder, restraint rule, and failure modes come from the *Beyond Prompting* course this repo distills.
