# Contributing

Thanks for wanting to contribute! This list curates **workflow recipes** — patterns that combine hooks, MCP servers, skills, agents, and CLAUDE.md to automate real tasks.

## What belongs here

A workflow is a **recipe that combines multiple Claude Code primitives** to accomplish a task. It should include:

- What the workflow does (the outcome)
- What components it uses (hooks, skills, MCP servers, agents, CLAUDE.md)
- How to set it up (install commands, config)
- A link to the source (GitHub repo, blog post, or gist)

**A single skill or a single hook is NOT a workflow.** See [awesome-claude-code-hooks](https://github.com/ithiria894/awesome-claude-code-hooks) for hooks and [awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) for skills.

## How to submit

1. Fork this repo
2. Add your workflow to the appropriate section in README.md
3. Follow the format: `- [Name](url) - Description of what the workflow does and what it combines.`
4. One workflow per PR
5. Submit a PR

## Quality standards

- The workflow must be something you have **actually used** or **thoroughly evaluated**
- It must combine at least 2 Claude Code primitives (e.g., hook + skill, MCP + agent)
- It must be actively maintained (last commit < 6 months)
- Description must start with capital letter and end with period

## Format

```
- [Workflow Name](https://github.com/user/repo) - What it does, combining X + Y + Z.
```
