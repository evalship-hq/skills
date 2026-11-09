# evalship skills

Your coding agent checks AI changes the way it runs tests: before it says a change to a prompt, a model or an LLM call is done, it runs the evals the change affects before and after, and [evalship](https://evalship.com) says whether it got worse beyond chance.

In Claude Code:

```
/plugin install evalship --marketplace evalship-hq/skills
```

In Codex, Cursor, Gemini CLI and other agents that read skills:

```sh
npx skills add https://evalship.com
```

## What your agent does with it

| When | It follows |
|---|---|
| It changes a prompt, a model or an LLM call | [compare.md](https://evalship.com/compare.md): the affected evals before and after, on your machine and keys. No account needed |
| Your repo is set up with evalship | [change.md](https://evalship.com/docs/agent), the line in your AGENTS.md: the change compared with your repo's history |
| You ask it to set up evals, or to run them on every pull request | [setup.md](https://evalship.com/setup.md) |
| You ask whether a pull request made your AI features worse | pr.md: the pull request's evals, compared with main |
| You want the same quality for less: a cheaper model, a shorter prompt | optimize.md: changes your evals can prove better |
| evalship's pull request comment lists eval flaws | the fix instructions in that comment |

The skill is one file, [skills/evalship/SKILL.md](skills/evalship/SKILL.md). The steps live on evalship.com, so they stay current without an update.

## What evalship gets

compare.md sends each try's result: whether it passed, why it failed, and its cost and time. It never sends code, inputs or replies, and evalship keeps none of it. The other pages say what they send before they send it. See [Security](https://evalship.com/security).

## tinyeval

This marketplace also lists [tinyeval](https://github.com/evalship-hq/tinyeval), a one-file bash eval runner for any language. Its skill keeps the checks your agent runs as test cases in your repo, with no account:

```
/plugin install tinyeval --marketplace evalship-hq/skills
```

## License

MIT
