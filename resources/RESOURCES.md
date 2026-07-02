# Further Resources

A short, curated reading/watching list. These are the ideas this workshop is built on — the LLM-wiki pattern, evaluation discipline, and the habit of staying the critical thinker in the loop. Each entry notes what it is and how it connects back to the material.

## The pattern itself

- **Andrej Karpathy — "LLM Knowledge Bases" (tweet)** — <https://x.com/karpathy/status/2039805659525644595>
  The viral post that kicked this off: instead of pointing LLMs only at code, use them to *build and maintain* a personal knowledge base on topics you care about. **How it relates:** this is the seed idea for the entire workshop — the wiki that compounds as you feed it sources.

- **Andrej Karpathy — `llm-wiki` gist** — <https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f>
  The follow-up write-up describing the architecture: immutable raw **sources**, an LLM-owned **wiki** of cross-linked markdown the model keeps current, and a **schema** doc guiding ingest / query / "lint" operations. The point is to move beyond plain RAG — the model reads a source once and integrates it, rather than re-retrieving every time. **How it relates:** this is the blueprint our `sources/`, `wiki/`, and `AGENTS.md` directly implement.

## Read

- **Hamel Husain & Shreya Shankar — Evals FAQ** — <https://hamel.dev/blog/posts/evals-faq/>
  A practical FAQ on evaluating LLM applications: error analysis as the highest-value activity, binary pass/fail over fuzzy rating scales, and custom annotation over generic metrics. **How it relates:** this is the backbone of Module 04 (the evaluation loop) — labeling failures and turning them into `AGENTS.md` improvements.

- **Ryan Lingo — "What Do We Mean by Learning?"** — <https://medium.com/p/709bbdbd06f8>
  Argues that "learning" hides several distinct kinds of work, and names eight of them (diagnostic, discovery, framing, generative, improvement, adaptive, meta, institutional). **How it relates:** gives vocabulary for the *learning log* — it helps you say which kind of learning a given entry actually captured.

- **a16z / Steven Sinofsky — on why AI is hard to diffuse through firms (tweet)** — <https://x.com/a16z/status/2042014774691819943>
  The argument that "algorithmic thinking" — being able to lay out the steps of your own work as a flowchart — is genuinely hard for most people, and that this, not the technology, is the real barrier to AI adoption. **How it relates:** explains *why* the workshop makes you write things down. `AGENTS.md` and the project log force you to make an implicit process explicit before an agent can run it.

## Watch

- **François Chollet — "It's Not About Scale, It's About Abstraction"** — <https://youtu.be/s7_NlkBwdj8>
  Chollet argues that scaling models up crushes known benchmarks but doesn't produce genuine intelligence; real intelligence is extracting reusable abstractions and recombining them (the ARC benchmark, deep learning + program synthesis). **How it relates:** the case for staying the critical thinker in the loop — the agent does pattern-matching legwork, but the abstraction, judgment, and acceptance stay yours.

- **Kenneth Stanley — "Why Greatness Cannot Be Planned"** — <https://youtu.be/lhYGXYeMq_E>
  On how rigid objectives can be deceptive, and how open-ended exploration often reaches places no fixed plan would. **How it relates:** mirrors how a wiki grows — every source you add and question you chase opens the next one; the compounding artifact is something you couldn't have fully specified up front.

## Books

- **Algorithms to Live By: The Computer Science of Human Decisions** — Brian Christian & Tom Griffiths
  Applies computer-science ideas — optimal stopping, explore/exploit, caching, scheduling — to everyday decisions. **How it relates:** the disciplined version of "use the lowest rung that works": when to stop tuning, when to keep exploring vs. exploit something that already works.

- **The Model Thinker: What You Need to Know to Make Data Work for You** — Scott E. Page
  Makes the case for reasoning with *many* models at once rather than one favorite frame. **How it relates:** the habit of mind a cross-linked wiki is built to support — holding multiple models of a problem and letting them check each other.
