# Backlog

A living document of everything that needs to be defined, designed, or built. Items are added as discovered and removed when complete.

---

## Workflows

Approach: define the user experience first, then move to implementation.
New workflows will be added as we discover them.

- [x] **First-time setup** — connecting Notion and Google Calendar (technical integration details to be resolved here)
- [ ] **Setup skill: guided onboarding** — the current skill only detects connection status and prompts the user to connect; improve it with step-by-step instructions, verification, and troubleshooting for both Notion and Google Calendar
- [ ] **First project creation** — the moment the user gets their first real value from the plugin

---

## Concepts to Define

Clear definitions that will shape every other decision.

- [ ] **Project** — what it is, minimum requirements, how it grows
- [ ] **Task** — unit of work within a project
- [ ] **Milestone** — meaningful checkpoint or deliverable
- [ ] **Role** — manager, contributor, viewer and what each can do
- [ ] **Context** — background information that lives in Notion and informs the assistant

---

## Design

- [ ] **Response design** — full pattern system: when to use bullet points vs prose, how many questions to ask at once, when to summarize vs go deep, overall tone
- [ ] **Proactivity: suggestions** — the assistant proactively recommends actions or surfaces relevant information
- [ ] **Proactivity: notifications** — the assistant alerts the user about time-sensitive events (deadlines, calendar conflicts, overdue tasks)

---

## Plugin Installation

How users install and activate the plugin on each supported platform.

- [ ] **Claude Code — plugin installation** — define the installation steps for Claude Code users (CLI-based, `claude mcp add`, plugin manifest discovery)
- [ ] **Claude.ai (co-work) — plugin installation** — define the installation steps for Claude.ai web users (UI-based onboarding, no CLI access)
- [ ] **ChatGPT — plugin installation** — define the installation steps for ChatGPT users (Actions integration, OpenAPI spec, GPT configuration)

---

## Platform Readiness

- [x] **Claude Code — complete plugin manifest** — `plugin.json` is missing `skills` and `mcpServers` declarations; Claude Code won't discover the skill or MCP config without them
- [ ] **Claude.ai — separate setup path** — the setup skill tells users to run `claude mcp add` (CLI only); claude.ai users need a web-UI-based onboarding path instead
- [ ] **ChatGPT — build Actions integration** — nothing exists yet; needs an OpenAPI spec describing available actions and the underlying endpoints to back them

---

## Architecture & Open Questions

- [ ] **Roles & permissions** — within a shared project, what can each role do? How does the assistant enforce this?
- [ ] **State & memory** — the orchestrator needs to track state across conversations; where does this live and how is it structured?
- [ ] **Plugin distribution & updates** — how does a user install this on Claude vs ChatGPT, and how do they receive updates?
- [ ] **Resumable workflows** — the orchestrator must track setup (and future workflow) progress across sessions so the user can complete configuration in multiple sittings without starting over. Decide where state lives and how the assistant detects and resumes an in-progress flow.
