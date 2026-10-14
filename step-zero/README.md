# Step Zero

A Claude Code skill that starts any AI build with the goal instead of the feature.

Most prompts start at Step 1: "Build this feature, it should do X, Y and Z." Step 0 is missing: what you want to achieve and how your workday should change after. Without it the AI does exactly what you said, including the parts that were a bad idea.

`/step-zero` interviews you one question at a time, researches what you are not sure about, and writes `concept.md`. From then on every task starts with "read concept.md", and the AI has enough context to tell you when the feature you asked for is the wrong way to reach the goal.

It also grills your idea: finds the assumptions that would kill it and the cheapest way to check each one.

## Install

Open Claude Code and say:

```
Install the step-zero skill from https://github.com/maxg-agency/skills
```

Or by hand, for all your projects:

```bash
git clone https://github.com/maxg-agency/skills.git ~/.claude/maxg-skills
ln -s ~/.claude/maxg-skills/step-zero ~/.claude/skills/step-zero
```

For one project only: copy this `step-zero` folder into `.claude/skills/` inside the project.

No Claude Code? Use [prompt.md](prompt.md): the same interview and the same grill as plain text for ChatGPT, Claude.ai or Gemini.

## Use

```
/step-zero                 start the interview, get concept.md
/step-zero research        competitors, audience, market, with sources
/step-zero grill           roast an idea or the existing concept.md
```

Or just say "let's start with the goal" or "grill my idea".

The interview asks six things, in this order:

1. Goal: what you want to achieve and how your day, numbers or business change after.
2. Who it is for: their problems, beliefs, what they have tried.
3. Where they come from and what they already know about you.
4. What you do not want: failure modes, out of scope.
5. Your concerns, all of them, each weighed by likelihood and damage.
6. Constraints: deadline, budget, stack, decisions already made.

Each question comes with the skill's own guess, marked as recommended, and two or three real alternatives. In Claude Code you answer with one click or type your own. In a plain chat the options come as a numbered list, so you can reply with a number.

If you answer "not sure", it does not move on. It researches the question and brings back options with sources. Three kinds of research, each saved to `research/`:

- Competitors: five to eight of them, first-screen promise, prices, free tier, what their users praise and complain about in public reviews, where everyone is weak.
- Audience portrait: built from what real people wrote in reviews and forums, grouped by what they wanted and what annoyed them, not by age or job title.
- Market and trends: size with the logic behind the number, growth, leaders, what is becoming the minimum users expect, each figure with a source and a date.

The result is `concept.md` in your project root, under two pages, in your words, with a mandatory section "Where the plan is weak". You confirm it, then you build.

## Why a file

A chat forgets. A file in the project root does not. Every agent, every session and every new feature reads the same two pages and argues with you from the same goal.

## Author

Max Gankov, founder of [Max G Agency](https://maxg.agency). I help founders grow products and bring AI into how their teams build.

- Website: https://maxg.agency
- LinkedIn: https://www.linkedin.com/in/max-gankov
- X: https://x.com/maxgankov

## License

MIT. See [LICENSE](../LICENSE).
