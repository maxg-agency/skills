# Step Zero

A Claude Code skill that starts any AI build with the goal instead of the feature.

Most prompts start at Step 1: "Build this feature, it should do X, Y and Z." Step 0 is missing: what you want to achieve and how your workday should change after. Without it the AI does exactly what you said, including the parts that were a bad idea.

`/step-zero` interviews you one question at a time, researches what you are not sure about, and writes `concept.md`. From then on every task starts with "read concept.md", and the AI has enough context to tell you when the feature you asked for is the wrong way to reach the goal.

It also grills your idea: finds the assumptions that would kill it and the cheapest way to check each one.

## Install

Claude Code, for all your projects:

```bash
git clone https://github.com/MaxFortus/step-zero.git ~/.claude/skills/step-zero-repo
ln -s ~/.claude/skills/step-zero-repo/step-zero ~/.claude/skills/step-zero
```

Or for one project only: copy the `step-zero` folder into `.claude/skills/` inside the project.

No Claude Code? Use [prompt.md](prompt.md): the same interview and the same grill as plain text for ChatGPT, Claude.ai or Gemini.

## Use

```
/step-zero                 start the interview, get concept.md
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

If you answer "not sure", it does not move on. It researches the question and brings back options with sources.

The result is `concept.md` in your project root, under two pages, in your words, with a mandatory section "Where the plan is weak". You confirm it, then you build.

## Why a file

A chat forgets. A file in the project root does not. Every agent, every session and every new feature reads the same two pages and argues with you from the same goal.

## License

MIT
