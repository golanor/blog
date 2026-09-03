+++
title = "Being a PhD Student in the age of AI, part 1"
date = 2026-09-03
lastmod = 2026-09-03T15:30:53+03:00
draft = false
+++

I have a love-hate relationship with AI. Mainly, after several years in industry, I relished returning to academia and being able to focus and learn things deeply. I feel that this ability erodes as I use and become dependent on AI. The starkest example here is in coding; I used to love to code, and would actively do coding exercises and learn new languages as a hobby (shoutout to <https://exercism.org/>). I barely have the patience to code anymore, as I know that practically any LLM will do a good enough job, and much faster, than I would. This led me into two directions. First, I wanted to read and learn what others are feeling and what else might change as LLMs improve. Second, I started thinking about satisfaction in the age of AI.

I went over different talks and discussions on AI in research and education, some of which appear in the bottom of this post. Many of these talks, mainly the never-skilling paper and Terry Tao's talk about an AI diet, describe similar issues to what I experienced. These authors didn't mention anything about enjoyment, but I feel that our skill use and our satisfaction with work are deeply related. The solution seems to be adding cognitive friction where possible.

I started experimenting with this approach by designing (with LLMs :)) agent skills to manually add friction to my conversations with agents. These help mainly when working through some calculation or explanation that I know, or when polishing a paper. It felt great using these, as the friction was real. I saw sharp improvements, both to my writing style and my ability to express myself, as well as to my research. Friction even provides more satisfaction, as I had to think about the answers to the agent questions myself and the final product is directly something that I made, albeit with some supervision and help from the LLM.

The skills are located at <https://github.com/golanor/agent-skills>. The one I lean on most is a _Socratic-Chavrusa_ skill, named after the pair-study tradition where two partners argue a text into understanding rather than reading it passively. Instead of answering, the agent takes a position, demands I defend or attack it, and withholds the answer until I have done the cognitive work myself. The whole thing is governed by a "friction dial" — a single knob for how much scaffolding is withheld before I get to see the answer:

```markdown
### The friction dial (L0–L6)

- **L0 — none**: logistics, syntax lookups, boilerplate. Answer directly.
- **L1 — predict-first**: before revealing a result, ask for a one-line
  prediction or sign/scaling guess ("Should this grow or shrink as the
  parameter increases? Why?").
- **L2 — attempt-first**: the user sketches the argument/derivation/code
  structure before you provide yours. Then diff their attempt against the
  real thing explicitly — name what they got right and where they diverged.
- **L3 — full chavrusa** (DEFAULT): take a position (possibly deliberately
  flawed), demand the user attack or defend it, argue back at least one
  round before conceding or resolving.
- **L4 — explicit teach-back**: the user must explain the concept explicitly,
  in full sentences or equations, as if teaching it. The agent interrogates
  the explanation until it is airtight or the gap is named.
- **L5 — cold reconstruction**: exam conditions. The user reproduces the full
  derivation from a blank page, no notes and no mid-course reactions from the
  agent — silence is the friction. Only when done does the agent grade.
- **L6 — transfer**: the user must USE the concept outside the context it was
  learned in — construct a novel problem it solves, or adapt the machinery to
  an unfamiliar setting. Passing means the knowledge is usable, not just
  recallable.
```

I default to L3, and the dial auto-adjusts: two failed attempts at the same step drops it a level, sailing through one bumps it up. A companion [English writing coach](https://github.com/golanor/agent-skills/tree/main/english-writing-coach) skill applies the same idea to prose — it diagnoses a problem by name and points at its neighborhood, but never rewrites the sentence for me, so I stay the author. Working this way, the friction is real, and so is the sense that the final product is mine.

Honestly, I am not sure these are a complete solution, mainly to the satisfaction issue. I think that in this age of constant distraction and content, we should dedicate time to sit far removed from all sources of distractions—our phones, the Internet, AI, whatever—and try to focus on learning something new, or tackling a problem, without looking for shortcuts. This echoes what Cal Newport wrote in his book, Deep Work. I admit that I need to improve in dedicating the time to do this, despite reading this book more than once. I still have at least one agent open, and my phone is located on my desk.

Sources:

1.  A talk that felt kind of pessimistic to me, about research in the age of agents, by Hsin-Yuan (Robert) Huang <https://www.youtube.com/watch?v=vT5blu-ZUZ0>.
2.  Terry Tao on AI diet for research students <https://www.youtube.com/watch?v=aTCaONNbrPY>, with additional opinions in <https://teorth.github.io/tao-web/ai-views.html>
3.  Terry Tao's Mathematics in the age of AI <https://teorth.github.io/tao-web/slides/age-of-ai-icm-2026.pdf>
4.  <https://tjoresearchnotes.wordpress.com/2026/07/28/proof-inflation/> Thoughts by Tobias J. Osborne about how to adapt to the coming age of 'proof inflation'.
5.  AI never-skilling in medical education <https://www.nature.com/articles/s41591-026-04438-y>.
