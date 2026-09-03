# Backlog

A living document of everything that needs to be defined, designed, or built. Items are added as discovered and removed when complete.

---

## Workflows

Approach: define the user experience first, then move to implementation.
New workflows will be added as we discover them.

- [ ] **First-time setup** — connecting Notion and Google Calendar (technical integration details to be resolved here)
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

## Architecture & Open Questions

- [ ] **Roles & permissions** — within a shared project, what can each role do? How does the assistant enforce this?
- [ ] **State & memory** — the orchestrator needs to track state across conversations; where does this live and how is it structured?
- [ ] **Plugin distribution & updates** — how does a user install this on Claude vs ChatGPT, and how do they receive updates?
