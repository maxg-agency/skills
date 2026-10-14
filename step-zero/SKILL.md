---
name: step-zero
description: Start any AI build with the goal, not the feature. Interviews the user one question at a time (goal, audience, where they come from, non-goals, concerns), researches what the user is unsure about, and writes concept.md that every later task starts from. Also grills an idea or an existing concept.md for the assumptions that would kill it. Use when the user says "/step-zero", "step zero", "let's start with the goal", "write the concept", "grill my idea", "roast my concept", or starts describing a new product, feature, landing page or campaign before any context exists.
---

# Step Zero

Most prompts start at Step 1: "Build this feature, it should do X, Y and Z."
Step 0 is missing: what you want to achieve and how your workday should change after.

This skill does Step 0 for the user. It asks the questions, does the research the user does not have time for, and writes `concept.md`. From then on every task in the project starts with "read concept.md", and the AI has enough context to push back when the feature asked for is the wrong way to reach the goal.

Two modes:

- **Interview** (default). Collect context, write `concept.md`.
- **Grill**. Stress-test an idea or an existing `concept.md`. Trigger words: grill, roast, stress-test, "what would kill this".

Answer in the language the user writes in. Write `concept.md` in that language too.

## Interview mode

### How to run the conversation

1. One question per message. Wait for the answer before the next one.
2. Start with the goal. When the user describes a solution ("I want a landing page", "I want a Telegram bot"), ask why, and ask what changes in their day or their business once it exists. Go one level up until you reach something the user actually wants, not something they plan to build.
3. For every question, offer your own guess as a recommended answer when you can make one from what the user already said. The user confirms or corrects, which is faster than writing from scratch.
4. When the user says "not sure" or "I don't know", do not move on. Offer to research it: competitors, best practices, references, how similar products handle it. Do the research with the tools you have (web search, reading the user's files) and bring back a short summary with sources. Then ask the user to pick.
5. Skip a question if the user has already answered it in passing. Say that you are skipping it and why.
6. If the user is in a project folder, read what is already there (README, docs, previous notes) before asking. Do not ask what the files already answer.

### The questions

Ask them in this order. Rephrase to fit the user's product; do not read them out as a form.

1. **Goal.** What do you want to achieve? How should your workday, your numbers or your business look after this exists? What would make you say in a month that it worked?
2. **Who it is for.** Who is the person on the other side? What problems do they have around this, what do they already believe, what have they tried? If there are several groups, which one matters first?
3. **Where they come from.** How does this person arrive: from an ad, a post, a search, a referral, a link in your product? What do they already know about you and your product at that moment? What mood and how much time?
4. **What you do not want.** What result would count as a failure even if the thing technically works? What should this not become? What is out of scope for now?
5. **Concerns.** Everything the user is worried about: the customer, the funnel, the texts, the structure, the tech, the price, the timing. Collect all of them, then weigh each one: how likely it is to be a real problem, how much damage it does, and what to do about it.
6. **Constraints.** Deadline, budget, stack, people, things that are already decided and not up for discussion.

After the last answer, say "I have enough. Writing concept.md." and write the file.

### concept.md

Write it to the project root (or where the user says). Structure:

```markdown
# <Project or feature name>: concept

Written <date> from an interview with <user>. Every task in this project starts with reading this file.

## Goal
What we want to achieve and how the day, the numbers or the business change after. One or two paragraphs, plus the one-month check: how we will know it worked.

## Who it is for
The person on the other side. Their problems around this, what they believe, what they have tried. If several groups: the primary one first, the others in a line each.

## Where they come from
How they arrive, what they already know, what state they are in.

## What we do not want
Failure modes even if the thing works. Out of scope for now.

## Concerns, weighed
| Concern | Likelihood | Damage | What we do about it |
One row per concern the user raised, plus any the interviewer added. Plain words, no scores without a reason.

## Constraints
Deadline, budget, stack, people, decisions already made.

## Open questions and research
What is still unknown, what was researched (with sources), what the user should decide next.

## Where the plan is weak
The interviewer's own view: two to five places where the current idea may not reach the goal, and what to check first.
```

Rules for the file:

- Write in the user's words where you can. Do not upgrade their phrases into jargon.
- Do not invent facts. A fact you do not have goes in square brackets as a question: `[how many visitors a month now?]`.
- "Where the plan is weak" is mandatory. If you think the plan is fine, say which part you checked and why it holds.
- Keep it under two pages. A concept nobody reads is not a concept.

After writing, show the "Where the plan is weak" section in the chat and ask the user to confirm or correct the file before any building starts.

## Grill mode

Input: an idea in a message, or an existing `concept.md`. If there is a `concept.md` in the project, read it first and do not ask what it already answers.

Goal: find the assumptions that would kill the idea if they turn out wrong, and the cheapest way to check each one.

1. Interview relentlessly, one question at a time. Walk down each branch of the idea: who pays, why now, why you, what they do today instead, what breaks at ten times the volume, what has to be true for the numbers to work. For each question give your recommended answer; the user confirms or corrects.
2. Do not accept adjectives as answers. "Better", "faster", "simpler" each get a follow-up: better than what, measured how.
3. When you have the picture, list the three to five assumptions whose failure kills the idea. For each: the assumption as a checkable sentence, why it is critical, how likely it is wrong and on what evidence, and the cheapest test (a conversation with five customers, a landing page with a small ad budget, a manual version of the service, a prototype in a day).
4. Order them by damage times likelihood. Say which one to test first and why.
5. If `concept.md` exists, append the result as a section `## Risky assumptions` and update "Where the plan is weak". If it does not exist, offer to run Interview mode and fold the grill into it.

Plain language throughout. No methodology terms, no frameworks by name. A founder who has never read a product book should understand every line.

## What this skill does not do

- It does not build anything. Building starts after the user confirms `concept.md`.
- It does not replace the user's judgment. It collects, weighs and points; the user decides.
- It does not ask for the sake of asking. If the user has given enough, write the file.
