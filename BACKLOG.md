# Backlog

A living document of everything that needs to be defined, designed, or built. Items are added as discovered and removed when complete.

---

## Workflows

Approach: define the user experience first, then move to implementation.
New workflows will be added as we discover them.

- [x] **First-time setup** — connecting Notion and Google Calendar (technical integration details to be resolved here)
- [ ] **Setup skill: guided onboarding** — step-by-step connect instructions now given for both Notion and Google Calendar (same Customize → Connectors flow for both, with surface-specific handling for Claude Code); still need re-verification after the user connects and troubleshooting for failed/stuck authorization
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

- [x] **Claude Code — plugin installation** — `/plugin marketplace add` + `/plugin install`, documented in README
- [x] **Claude Cowork — plugin installation** — same plugin manifests, installed via Customize → Plugins → Add marketplace in the UI (no CLI, no separate packaging needed), documented in README
- [x] **Claude Cowork — compatibility check** — verified plugin/MCP/skill behavior matches Claude Code (same built-in Google Calendar/Drive connectors, same manifest schema); fixed a real bug found along the way: `.mcp.json`'s `notion` entry was missing `"type": "http"`, which silently broke the connection on both platforms
- [x] **Notion/Calendar UX parity** — Notion was previously bundled via `.mcp.json` (`mcp.notion.com`), giving it a smoother inline-OAuth-URL experience than Google Calendar (which has no shared multi-tenant client — Google's official Calendar MCP server requires each user to register their own GCP OAuth credentials). Rather than upgrade Calendar to match, we downgraded Notion: removed `.mcp.json` and `plugin.json`'s `mcpServers` entry, and now rely on Claude's built-in Notion connector (Customize → Connectors) just like Calendar. Trade-off accepted deliberately: consistency of experience over the smoother but asymmetric one-click Notion flow.
- [x] **Fix wrong connector instructions on Claude Code** — real-world test on Claude Code surfaced two bugs in the setup skill: (1) it said "Settings → Connectors" when the actual UI label is "Customize → Connectors"; (2) it gave GUI-app instructions (Customize menu) to a Claude Code CLI session, which has no such menu at all — connectors there are managed on claude.ai/Desktop and carry over automatically. Skill now branches instructions by which surface it's running in.

---


## Architecture & Open Questions

- [ ] **Roles & permissions** — within a shared project, what can each role do? How does the assistant enforce this?
- [ ] **State & memory** — the orchestrator needs to track state across conversations; where does this live and how is it structured?
- [ ] **Plugin distribution & updates** — how does a user install this on Claude, and how do they receive updates?
- [ ] **Resumable workflows** — the orchestrator must track setup (and future workflow) progress across sessions so the user can complete configuration in multiple sittings without starting over. Decide where state lives and how the assistant detects and resumes an in-progress flow.
