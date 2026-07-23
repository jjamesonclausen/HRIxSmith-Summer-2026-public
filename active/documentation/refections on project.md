# Reflections on the Project (LLM written)

## Building the Wiki

One of the most valuable parts of this project has been building an LLM wiki that gives us a way to work with a large amount of research without losing track of it. The goal is not simply to collect papers. It is to create a system where we can ask questions, trace ideas back to sources, and make connections among VAWT designs, parameters, fluid-dynamics concepts, and project decisions.

I have learned that the organization of the wiki matters just as much as the amount of information in it. We have had to correct summaries, broken links, formatting, images, metadata, and source-conversion problems. Those issues made it clear that an LLM-generated knowledge base cannot be treated as finished just because it looks polished. It needs structure, rules, and regular checking.

I have also been thinking about how the wiki can be more useful for learning. For example, automatic links between terms and concept pages could help show relationships, but too many links could make the connections less meaningful. Tags for important design choices may be more useful for seeing the bigger picture. The point is to build a tool that helps us understand the project, not just one that stores information.

## Using an LLM for Design Decisions

The LLM has been very useful for comparing designs quickly. Weighted decision tables and several different ranking perspectives helped us narrow the VAWT concepts we wanted to investigate. Instead of relying on one answer, we compared rankings from different viewpoints and compared them with our own reasoning. This made the decision process more visible and gave us a way to question the results rather than simply accepting one recommendation.

At the same time, I do not think speed alone makes a decision trustworthy. I have been concerned about whether we can trust rankings or numerical comparisons when some information is missing or inconsistent. A qualitative ranking may sound convincing, and a number may look precise, but either can be misleading if the source information is incomplete or interpreted incorrectly. The LLM is helpful for organizing and comparing evidence, but it does not replace checking the evidence or making our own judgment.

## Learning Versus Letting the Tool Do the Work

The biggest question I have about this project is how to use AI to learn without letting it do the learning for us. The LLM can synthesize information across many sources and answer almost any question we think to ask. In that sense, it feels like having access to an expert research partner. It can give us a much broader picture of the field than we could build quickly on our own.

However, that same speed can remove some of the struggle that normally forces a person to understand technical concepts. If the LLM ranks designs or explains CFD settings before we have worked through the concepts ourselves, it is easy to become a passive user of the tool. I think we need to be intentional about using the LLM as a teacher: asking it to quiz us, explain competing viewpoints, show the reasoning behind a decision, and help us identify what we still do not understand.

This has changed how I think about the final product of the project. The project is not only about producing a good VAWT design. It is also about documenting how a future team can use an LLM or other AI tools to learn, research, organize evidence, and support engineering work without giving up responsibility for the decisions.

## Limits of AI-Generated Work

The work with CAD and CFD has made the limitations of AI tools especially clear. ZooKeeper is promising because it can create a turbine model quickly, but I have seen it change parts of a design that were already working when asked to modify something else. That makes me question whether a quickly generated model has a structure that is reliable enough for later iteration. I also found it frustrating when I could not directly control or manually edit the changes. Being able to see what code changed is important if we want to understand and maintain the model ourselves.

CFD has raised a similar issue. A simulation can produce a result, but that does not mean the result is valid. We have had to question geometry, setup choices, dimensionality, mesh settings, reference data, and the way results are interpreted. The LLM can help troubleshoot or suggest what to investigate, but it cannot remove the need to validate the setup and compare results with trustworthy references.

## Moving Forward

I want to keep using the LLM wiki and AI tools because they make research, comparison, and iteration much faster. But I also want the process to remain transparent and educational. The tools should help us ask better questions, see more possible approaches, and organize our evidence. They should not become a reason to skip the reasoning, validation, and learning that make an engineering project meaningful.

This reflection represents Julie's observations from the first four weeks of the project, rather than independently validated conclusions about LLMs, AI CAD tools, or CFD software generally. (source: active/_Julie_daily_log.md)
