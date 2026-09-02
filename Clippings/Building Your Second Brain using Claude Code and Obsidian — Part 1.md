---
title: "Building Your Second Brain using Claude Code and Obsidian — Part 1"
source: "https://medium.com/@tom.5610/building-your-second-brain-using-claude-code-and-obsidian-part-1-c67e0b97556b"
author:
  - "[[Tom Liu]]"
published: 2026-05-06
created: 2026-09-02
description: "The bottleneck in my learning was never finding good content — it was the grunt work after reading it — summarizing, connecting ideas across"
tags:
  - "clippings"
---
The bottleneck in my learning was never finding good content — it was the grunt work after reading it — summarizing, connecting ideas across articles, filing things where I’d actually find them again. I read technical blogs constantly, but I just… didn’t do any of that. For years, knowledge entered, sparked something, and faded — scattered across browser tabs and half-started notes I’d never reopen.

Then I came across Andrej Karpathy’s [tweet](https://x.com/karpathy/status/2039805659525644595) and something clicked. What if the LLM didn’t just *answer questions* about my documents — what if it *transformed* them into structured knowledge? A persistent wiki where concepts are linked, connections are surfaced, and rationale is made explicit. From there, I could drill down into the relationships between ideas, and bring my own lens to deep-dive into the topics that matter to me.

The idea is awesome; however, Andrej didn’t share ‘step-by-step’ guidance. Others have reproduced his method in different forms — using the llm-wiki gist as a system prompt, creating reusable skills, even building apps. I wasn’t happy with the results, so I decided to build my own approach using Claude Code and Obsidian.

Here’s a sneak peek before we dive in. Say you’re reading Anthropic’s engineering blog — [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents), what if you could transform it into a wiki and navigate the key parts using Obsidian:

![](https://miro.medium.com/v2/resize:fit:1400/format:webp/0*fs5t-znKKm-cYymQ.png)

## Andrej’s llm-wiki

The purpose of [llm-wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) is to build personal wiki knowledge bases for topics you care about. It has three flows: ingest (transform documents into structured wiki pages), query (ask questions with citations), and maintenance (keep the wiki healthy over time). This post covers ingest, Obsidian and Obsidian Web Clipper setup. The rest will be covered in Part 2.

Here’s a reference architecture:

![](https://miro.medium.com/v2/resize:fit:1400/format:webp/0*gzcmgKtt4F629j1_.png)

## How It Works

The whole process standardizes the wiki generation, from flat documents to structured knowledge. I built a plugin so you can do this repeatably.

Here’s what the pipeline looks like conceptually:

![](https://miro.medium.com/v2/resize:fit:1400/format:webp/0*lphJDxaYRzksjoBk.png)

To build the `ingest` process, the handy way is to use an AI coding agent (Claude Code, Kiro, Codex, etc.) with Andrej’s recipe.

Luckily, Andrej shared his recipe — [llm-wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) gist. The simplest approach: paste the gist into Claude Code and point it at your source document. This works, but doesn’t guarantee consistent quality and ties you to a single session. To make it repeatable, I built a plugin — [llm-wiki plugin](https://github.com/tom5610/llm-wiki/tree/main) — that encodes the pipeline as reusable skills I can refine over time.


## Reference Resources

- [llm-wiki plugin](https://github.com/tom5610/llm-wiki/tree/main) — my curated llm-wiki skills
- [llm-wiki](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f) gist — Andrej Karpathy’s llm-wiki recipe
- [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)