# Skills

Small, self-contained skills for building products with AI. Each one fixes a single step that most people skip or rush.

Every skill lives in its own folder and works on its own. Each comes in two versions: a Claude Code skill, and a plain prompt you can paste into ChatGPT, Claude.ai or Gemini.

| Skill | What it does |
|---|---|
| [step-zero](step-zero/) | Starts any build with the goal, not the feature. Interviews you, researches what you are unsure about, writes `concept.md`, grills the idea. |

More are coming. Watch the repository to get them.

## Install

The easy way: open Claude Code and say

```
Install the step-zero skill from https://github.com/maxg-agency/skills
```

By hand, for all your projects:

```bash
git clone https://github.com/maxg-agency/skills.git ~/.claude/maxg-skills
ln -s ~/.claude/maxg-skills/step-zero ~/.claude/skills/step-zero
```

Repeat the second line for every skill you want. To update later: `cd ~/.claude/maxg-skills && git pull`.

For one project only: copy the skill folder into `.claude/skills/` inside the project.

No Claude Code? Open the skill folder and use its `prompt.md`.

## Author

Max Gankov, founder of [Max G Agency](https://maxg.agency), an AI automation agency for tech and service companies with a team.

- Website: https://maxg.agency
- LinkedIn: https://www.linkedin.com/in/max-gankov
- X: https://x.com/maxgankov

## License

MIT. See `LICENSE`.
