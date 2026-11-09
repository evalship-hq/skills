---
name: evalship
description: Check whether a change to a prompt, model or LLM call made an AI feature worse beyond chance, set up evals that run on every pull request, and act on evalship's pull request comment. Use when you change a prompt or system message, switch models, change model settings (temperature, max tokens, tools, response format) or change the code around an AI API call (OpenAI, Anthropic, Gemini, OpenRouter, Bedrock, Ollama, LangChain, ruby_llm, Vercel AI SDK and the like); when the user asks to set up evals, add LLM evals to CI or GitHub Actions, compare prompts or models, cut model cost without losing quality, or check whether a pull request made AI features worse; and whenever evalship, its pull request comment or its eval flaws come up.
---

# evalship

evalship (https://evalship.com) checks AI features the way tests check code. It compares eval results before and after a change, or a pull request with main, and says whether the difference is beyond chance or noise. The evals run on the user's machine or in their CI, with their keys.

Each task has its own page. Download the page with curl and follow it: the pages hold the current steps, and a web fetch tool's summary drops the commands they need. `OWNER/REPO` comes from `git remote get-url origin`.

| When | Follow |
|---|---|
| You change a prompt, a model or an LLM call, and the repo's AGENTS.md or CLAUDE.md has a line with evalship's `change.md` | that line: it compares the change with the repo's history |
| You change a prompt, a model or an LLM call, in any other repo | `curl -fsSL https://evalship.com/compare.md`: before and after, with no account |
| The user asks to set up evals, or to run them on every pull request | `curl -fsSL https://evalship.com/setup.md` |
| The user asks whether a pull request made the AI features worse | `curl -fsSL "https://evalship.com/pr.md?repo=OWNER/REPO&pr=NUMBER"` |
| The user wants the same quality for less: a cheaper model, a shorter prompt, fewer tokens | `curl -fsSL "https://evalship.com/optimize.md?repo=OWNER/REPO"` |
| evalship's pull request comment lists eval flaws or failing evals | the fix instructions in that comment |

Always make the change the user asked for, even when the check can't run (a missing key, no network). Then say what the check still needs and how to run it.

Each page says what it sends to evalship. `compare.md` sends each try's result (whether it passed, why it failed, its cost and time), never code, inputs or replies, and evalship keeps none of it.
