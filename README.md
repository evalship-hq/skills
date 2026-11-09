# evalship skills

Your coding agent checks AI changes the way it runs tests: before it says a change to a prompt, a model or an LLM call is done, it runs the evals the change affects before and after, and [evalship](https://evalship.com) says whether it got worse beyond chance.

In Claude Code:

```
/plugin install evalship --marketplace evalship-hq/skills
```

In Gemini CLI:

```sh
gemini extensions install https://github.com/evalship-hq/skills
```

In Codex, Cursor and other agents that read skills:

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
| You ask it to monitor your AI calls in production | [production.md](https://evalship.com/docs/monitor): your app sends each AI call, and evalship emails you when one fails |
| evalship's pull request comment lists eval flaws | the fix instructions in that comment |

The skill is one file, [skills/evalship/SKILL.md](skills/evalship/SKILL.md). The steps live on evalship.com, so they stay current without an update.

## What evalship gets

The skill sends data only to evalship.com, and each page says what it sends before it sends it.

- **compare.md**, with no account: each try's result, meaning whether it passed, why it failed, and its cost and time. Never code, inputs or replies, and evalship keeps none of it.
- **change.md**, for a repo connected to evalship: the eval results and the diff of the change. The diff is deleted once a commit of the same code reaches GitHub, or after 7 days.
- **production.md**, for a repo connected to evalship: what each AI call your app sends got and answered, its session and the user id you send (send a hash). Kept with your plan's history, as eval results are, and shown only to the repo's members.
- **setup.md, pr.md and optimize.md**, for a repo connected to evalship: eval results, kept with your plan's eval history (30 days on Free, up to two years on Business). Owners can stop evalship keeping eval inputs and outputs.

Your evals run on your machine or in your CI, with your keys. evalship never gets your secrets or a copy of your repository. [Security](https://evalship.com/security) and [Privacy](https://evalship.com/privacy) have the details.

## tinyeval

This marketplace also lists [tinyeval](https://github.com/evalship-hq/tinyeval), a one-file bash eval runner for any language. Its skill keeps the checks your agent runs as test cases in your repo, with no account:

```
/plugin install tinyeval --marketplace evalship-hq/skills
```

## License

MIT
