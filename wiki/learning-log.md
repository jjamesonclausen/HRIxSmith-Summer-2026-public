# Learning Log

The running record of **you getting smarter**. Whenever you genuinely learn something, capture it here — in your own words, not pasted from the model. This is the twin of the [project log](log.md): that one tracks the work, this one tracks your understanding.

Write entries yourself. An entry that is just copied agent output is the tell that you skipped the thinking.

## Entry format

```text
## [marker] the concept
- In my words:  your own explanation, no peeking
- Tripped me up: what was confusing at first, and what cleared it
- Still open:   a question you would chase next
```

---

## What an LLM wiki is - Anna
- An LLM wiki works by ingesting sources that you provide (as Markdown files in the sources folder) and writing wiki pages that summarize the sources and explain concepts that appear across sources. This results in an organized knowledge base from which you can learn by having the agent engage you in discussion, answer questions, quiz you, etc. The agent should ONLY pull information directly from the sources and NEVER edit the sources. When you discuss the information and ask questions, the agent will document new connections you make in the wiki. All sources should be Markdown files because they don't depend on any outside systems or companies and can be opened in any editor.
- Tripped me up: I was confused about the relationship between vs-code, opencode, openAI and obsidian. Now I understand that openAI is the LLM that is powering the LLM wiki, opencode is a framework that lets you work with various LLMs in a programming-like format (slightly unclear about this still). VS-code can be used to run opencode and visualize the folders while obsidian can be used to visualize the folders and do fancy stuff with how you look at the data within them. I need to figure out how to do the cool obsidian things.
- Still open: I'm still thinking about the ways this LLM wiki model can be useful (and how it can be applied) while being cautious about trusting it too much and allowing it to do tasks for me that I want to have the skills to do myself. However, after just being quizzed by it about a paper, it did make me read and actually synthesize the information for myself more deeply than I would've otherwise. I think the agent needs work though bc its questioning got very redundant when I didn't say the exact thing it wanted me to. Another thought: I don't want my writing to start to sound like AI after interacting so much with AI text. I fear it's already beginning though. And even reading Ryan's article I thought it sounded a bit AI ish (or maybe just too corporate for my ears) idkkk 
  
## va1 paper synthesis - Anna
- The amount of time (annually) spent with higher or lower speed wind conditions is the main determining factor for VAWT choice. Darrius turbines produce the majority of their power during high wind speed events and are thus much more effective in locations where higher speed winds dominate. If there is a significant portion of time with only lower wind speeds Savonius turbines are equal or better than Darrius as they can self start in very low winds and generate power during those winds where Darrius turbines would not.
- Tripped me up: I initially didn't emphasize the importance of the percentage of time in a year with higher vs lower wind speeds. This is very important, more so than just what's the max wind speed or even what is the median or average.
- Still open: Need ways to get really accurate wind data and model turbulence and change in direction. Because I'd imagine that a Darrius would struggle with wind that constantly changed direction bc it would be slowed down and have to restart in a different direction.

### 2026-06-25 — action log - Anna
Task: consolidate wiki pages to reduce confusion

Actions:
- Deleted /questions folder (and associated instructions in AGENTS.mg), moved the wiki page inside it to concpets.

Open:
- considering more organized structure within concepts folder

## va2 paper synthesis - Anna
- Airfoil design was theoretically optimized using a cheaper and faster method than traditional CFD which is computationally expensive. CST parameterization was used to turn airfoil shape into an expression that was simplified to the most important seven parameters. They played around with those to determine which parameter affected which part of the airfoil shape and how, and then to determine which influenced the Cp the most. The estimations of Cp were done with Kriging which is a cheaper way to predict Cp than CFD. Kriging has a stochastic residual term to capture randomness and a polynomial deterministic term as well as a corrective kernel that pulled the prediction closer to known points. Latin-hypercube sampling was used to generate possible airfoil designs with the CST parameterization in a way that ensured they would be well spread out across all possibilities. Kriging predicted the Cp for those and then MIGA was used to search the possibilities and select the best ones. MIGA is a genetic algorithm that uses islands on which populations evolve and occasionally migrate. The best airfoils were analyzed with CFD to verify their performance.
- Tripped me up: I was really confused about Kriging and didn't really understand the role of Kriging vs Latin-hypercube sampling. Some of the equations were also unclear to me.
- Still open: I think I understand the process much better, if we want to look into this again I would want to learn more about how all of the steps work.

## 2026-06-30 — Schema instruction design - julie 
- Explained: How to tighten a schema procedure so future PDF figure extraction consistently uses Python/PyMuPDF, checks for existing source/image mappings, links images from `sources/*.md`, and verifies counts/paths/order before finishing.
- Prompt for Anna: Add your own note here if the idea of turning a successful workflow into a reusable schema rule clicked.

## 2026-06-30 — Torque ripple - julie 
- In my words: Torque ripple is when torque is not smooth while the turbine rotates, so it rises and falls instead of staying steady. Those fluctuations can reduce efficiency.
- Tripped me up: I hadn't heard the term before but it just means uneven torque over the rotation.
- Still open: How much torque ripple matters depends on the turbine design and operating point.

## 2026-07-01 — PDF ingest and OCR - julie
- In my words: Learned about how the LLM processes PDFs, what OCR is, and why errors can happen when turning a PDF into Markdown. I understand better now how to prompt it when ingesting PDFs.
- Tripped me up: I was not clear on why the markdown could end up missing or summarizing text even when the PDF looks readable and i can highlight the text.
- Still open: How to have it systematically check the new markdown so it does not summarize or miss text.
