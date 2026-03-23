# Awesome Claude Code Workflows [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Curated workflow recipes that combine hooks, MCP servers, skills, agents, and CLAUDE.md to automate real development tasks in Claude Code.

A workflow is more than a single tool — it's a **recipe** that chains multiple Claude Code primitives together. Think of this as a cookbook, not a tool catalog.

Looking for individual components? See [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) for tools, [awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) for skills, and [awesome-claude-code-hooks](https://github.com/ithiria894/awesome-claude-code-hooks) for hooks.

## Contents

- [Virtual Engineering Teams](#virtual-engineering-teams)
- [Plan-Build-Review Pipelines](#plan-build-review-pipelines)
- [TDD and Code Quality](#tdd-and-code-quality)
- [Git and PR Automation](#git-and-pr-automation)
- [Multi-Agent Orchestration](#multi-agent-orchestration)
- [Ship and Deploy](#ship-and-deploy)
- [Research and Discovery](#research-and-discovery)
- [Browser and Testing](#browser-and-testing)
- [Marketing and Content](#marketing-and-content)
- [Business Operating Systems](#business-operating-systems)
- [Autonomous Loops](#autonomous-loops)
- [Scope and Config Management](#scope-and-config-management)

---

## Virtual Engineering Teams

Workflow systems that simulate an entire engineering team with specialized agents.

- [gstack](https://github.com/garrytan/gstack) - Virtual engineering team with 25 skills — CEO review, design review, eng review, QA, ship, canary deploy, freeze/guard safety hooks, and browser-based testing. The gold standard for "skills + hooks + CLAUDE.md as a startup engineering org."
- [Superpowers](https://github.com/jasonm/superpowers) - Composable plugin with auto-triggering skills for TDD, brainstorming, plan-then-execute, subagent-driven development, parallel agent dispatch, and code review loops. Includes hooks for session-start and verification gates.
- [Everything Claude Code](https://github.com/nicholasareed/everything-claude-code) - Comprehensive agent harness with 28 agents, 60+ commands, 100+ skills, hook profiles (minimal/standard/strict), language-specific rules for 12 languages, and autonomous loop management.
- [Solopreneur Plugin](https://github.com/codeislaw1993/solopreneur-plugin) - Turns Claude into a virtual company with 6 specialist agents (engineer, designer, QA, researcher, bizops, content strategist). Full product lifecycle: discover → spec → backlog → design → build → review → ship. Includes decision journal and observer protocol.

## Plan-Build-Review Pipelines

Workflows that structure the development cycle into distinct planning, building, and review phases.

- [gstack autoplan](https://github.com/garrytan/gstack) - Auto-chains CEO review → design review → eng review into a single pipeline. Each review phase has its own checklist and acceptance criteria. Found in `/autoplan/SKILL.md`.
- [Superpowers plan-execute](https://github.com/jasonm/superpowers) - Two-phase workflow: `/write-plan` creates a structured plan, `/execute-plan` implements it step by step with verification gates between steps. Found in `skills/writing-plans/` and `skills/executing-plans/`.
- [Solopreneur sprint](https://github.com/codeislaw1993/solopreneur-plugin) - Parallel feature building with isolated git branches per feature, auto git checkpointing after every skill completion, and agent team kickoff meetings where agents debate approach.

## TDD and Code Quality

Workflows that enforce test-driven development and automated code quality checks.

- [Superpowers TDD](https://github.com/jasonm/superpowers) - Full red-green-refactor loop: write failing test → implement → verify → refactor. Auto-triggers verification before marking any task complete. Found in `skills/test-driven-development/`.
- [Everything Claude Code TDD](https://github.com/nicholasareed/everything-claude-code) - TDD workflow with autonomous loop support — agent keeps running test cycles until all pass. Found in `skills/tdd-workflow/`.
- [gstack QA](https://github.com/garrytan/gstack) - Browser-based QA that opens real pages with Playwright, takes screenshots, and validates against acceptance criteria. Found in `skills/qa/`.
- [Superpowers code review loop](https://github.com/jasonm/superpowers) - Two-skill combo: `/requesting-code-review` prepares the review request, `/receiving-code-review` processes feedback. Uses a dedicated code-reviewer agent. Found in `skills/requesting-code-review/` and `agents/code-reviewer.md`.

## Git and PR Automation

Workflows that automate git operations, branching strategies, and pull request management.

- [Superpowers git worktrees](https://github.com/jasonm/superpowers) - Run parallel workstreams using git worktrees — each agent works in its own isolated copy of the repo. Found in `skills/using-git-worktrees/`.
- [gstack ship pipeline](https://github.com/garrytan/gstack) - Full deploy pipeline: merge PR → deploy → post-deploy monitoring loop. Chains `/ship` → `/land-and-deploy` → `/canary` skills. Found in `skills/ship/`, `skills/land-and-deploy/`, `skills/canary/`.
- [Autoresearch branch-per-run](https://github.com/karpathy/autoresearch) - Creates a new git branch for each autonomous experiment run (`git checkout -b autoresearch/<tag>`), tracks results in `results.tsv`, keeps or discards based on evaluation.

## Multi-Agent Orchestration

Workflows that coordinate multiple AI agents working in parallel or sequence.

- [Superpowers parallel dispatch](https://github.com/jasonm/superpowers) - Dispatch multiple subagents in parallel, each working on independent subtasks. Includes patterns for collecting results and merging. Found in `skills/dispatching-parallel-agents/`.
- [Superpowers subagent-driven development](https://github.com/jasonm/superpowers) - Main agent breaks work into subtasks, delegates to specialist subagents, reviews their output. Found in `skills/subagent-driven-development/`.
- [Everything Claude Code orchestrate](https://github.com/nicholasareed/everything-claude-code) - Multi-agent orchestration command that coordinates agents across different roles. Found in `commands/orchestrate.md`.
- [Founder OS queue system](https://github.com/danielraffel/founder-os) - Queue-based task processing where agents pick up work items autonomously: `/queue:add` → `/queue:work` → `/founder:review`. Includes dependency management and blocked_by ordering. Found in `.claude/queue/`.
- [Solopreneur kickoff](https://github.com/codeislaw1993/solopreneur-plugin) - Agent team meetings where 6 specialist agents debate approach before building. Found in `skills/kickoff/`.

## Ship and Deploy

Workflows for publishing packages, deploying applications, and monitoring releases.

- [gstack canary deploy](https://github.com/garrytan/gstack) - Post-deploy monitoring loop that watches for errors after canary release. Chains deploy → monitor → rollback-if-needed. Found in `skills/canary/`.
- [MCP listing pipeline](https://github.com/mcpware/claude-code-organizer) - End-to-end MCP server publishing: npm publish → GitHub Actions CI/CD → Glama registry → mcp.so → Official MCP Registry → Plugin Marketplace. Documented in `3-ship/playbooks/mcp-listing-playbook.md`.

## Research and Discovery

Workflows for market research, codebase exploration, and knowledge gathering.

- [Everything Claude Code search-first](https://github.com/nicholasareed/everything-claude-code) - Research before coding — agent searches codebase, docs, and web before writing any code. Found in `skills/search-first/`.
- [Autoresearch autonomous loop](https://github.com/karpathy/autoresearch) - Karpathy's autonomous AI research agent: modify code → train for 5 min → evaluate → keep/discard → repeat. Uses `program.md` as the skill file that instructs the loop.
- [Everything Claude Code continuous learning](https://github.com/nicholasareed/everything-claude-code) - Auto-extracts patterns from coding sessions into reusable skills. The agent learns from its own work. Found in `skills/continuous-learning/`.

## Browser and Testing

Workflows that combine browser automation with Claude Code for testing and data gathering.

- [gstack browser QA](https://github.com/garrytan/gstack) - Opens real web pages via Playwright, takes screenshots, validates UI against acceptance criteria. Found in `skills/qa/`.
- [UI Annotator + Claude Code](https://github.com/mcpware/ui-annotator-mcp) - Annotate any web page with hover labels, then tell Claude which element to change by name. Combines MCP server (reverse proxy) with Claude Code conversation. Zero extensions, any browser.
- [Pagecast demo recording](https://github.com/mcpware/pagecast) - Record browser sessions as GIF/WebM/MP4 via MCP. Tell Claude what to demo, it opens a browser, performs actions, and exports the recording.

## Marketing and Content

Workflows for content creation, social media posting, and distribution.

- [Agency Agents marketing suite](https://github.com/AidenYangX/agency-agents) - 144+ agent personas including 30+ marketing specialists (SEO, Reddit, TikTok, content strategy). Install script converts to Claude Code, Cursor, or Copilot format.
- [OPC Skills solopreneur marketing](https://github.com/leoncvlt/opc-skills) - 10 standalone skills for solopreneurs: SEO/GEO optimization, Reddit research, Product Hunt search, domain hunting, logo creation, banner creation.
- [Everything Claude Code content engine](https://github.com/nicholasareed/everything-claude-code) - Skills for article writing, market research, and investor materials. Found in `skills/content-engine/`, `skills/market-research/`.

## Business Operating Systems

Complete systems that use Claude Code as the operating layer for running a business.

- [Founder OS](https://github.com/danielraffel/founder-os) - Queue-based markdown OS: autonomous task processing, research pipelines, institutional memory (`.claude/learnings/`), context budgeting, goal-backward verification. Everything is markdown files — zero infrastructure.
- [BOS-AI](https://github.com/SynapticAGI/BOS-AI) - Business Operating System with 30 agents across 10 categories, missions (pre-configured workflow templates), and the Business Chassis formula: Profit = Prospects x Lead Conv x Client Conv x Avg Spend x Frequency x Margin.
- [ABF (Agentic Business Framework)](https://github.com/agent-business-framework/abf) - Full TypeScript runtime for agent-as-employee companies. Seed-to-company pipeline: upload business plan → LLM generates agent team + workflows. YAML workflow definitions, approval queues, behavioral bounds.

## Autonomous Loops

Workflows where Claude Code runs continuously without human intervention.

- [Everything Claude Code autonomous loops](https://github.com/nicholasareed/everything-claude-code) - Start and manage autonomous agent loops that keep running until a goal is met. Commands: `/loop-start`, `/loop-status`. Found in `skills/autonomous-loops/` and `skills/continuous-agent-loop/`.
- [Autoresearch experiment loop](https://github.com/karpathy/autoresearch) - Agent autonomously modifies code, runs 5-minute experiments, evaluates results, and repeats. No human in the loop during runs.

## Scope and Config Management

Workflows for managing Claude Code's own configuration across scopes.

- [Claude Code Organizer](https://github.com/mcpware/claude-code-organizer) - Web dashboard + MCP server that scans `~/.claude/`, shows scope hierarchy (Global → Workspace → Project), and lets you drag-and-drop config between scopes. 4 MCP tools for programmatic scope management.
- [gstack freeze/guard/unfreeze](https://github.com/garrytan/gstack) - Hook-based safety system to prevent changes to critical files. `/freeze` locks files, `/guard` enforces during session, `/unfreeze` removes protection. Found in `skills/freeze/` and `skills/guard/`.

---

## Related Awesome Lists

- [awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code) - Comprehensive catalog of Claude Code tools, skills, hooks, agents, and plugins.
- [awesome-claude-code-hooks](https://github.com/ithiria894/awesome-claude-code-hooks) - Curated collection of Claude Code hooks for event-driven automation.
- [awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) - The definitive list of MCP servers.
- [awesome-claude-skills](https://github.com/ComposioHQ/awesome-claude-skills) - Claude Code skills collection.
- [awesome-vibe-coding](https://github.com/filipecalegario/awesome-vibe-coding) - Vibe coding tools and resources.

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines. We curate, not collect — not every submission will be accepted.
