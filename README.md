# Personal Project Manager

An AI-native plugin that turns any compatible AI assistant into a personal project management co-pilot — one conversation at a time.

## What is this?

This is a **skill set / plugin** designed to be installed on AI assistants (starting with Claude, then ChatGPT via Custom GPTs with Actions, with others to follow). Once installed, the assistant becomes capable of managing projects on behalf of the user, guiding them through setup, tracking progress, and helping coordinate work across time.

The core idea is simple: **one point of interaction**. The user never leaves the chat. The assistant handles the rest.

## Core Concepts

### The Orchestrator
At the heart of this plugin is an orchestrator — a persistent workflow engine that knows the state of everything. It tracks what has been configured, what is pending, and what should happen next. This is not just an onboarding wizard; it stays active throughout the lifecycle of every project, guiding the user at every step.

### Two Layers, Clearly Separated

| Layer | Scope | Storage | Sharing |
|---|---|---|---|
| **Calendar** | Personal | Connected calendar (e.g. Google Calendar) | Never shared |
| **Projects** | Collaborative | Notion | Shared with teammates |

A person has one calendar and many projects. A project can have many people. These two layers never mix — the assistant is the bridge between them.

### The Assistant as Scheduling Advisor
When tasks are assigned or deadlines approach, the assistant helps the user fit that work into their personal calendar. It understands the full picture — all active projects, all commitments — and negotiates between what the project needs and what the user's time actually allows.

## Key Features

- **Multi-project management** — handle multiple projects simultaneously from a single chat interface
- **Project collaboration** — projects can be shared with other people, leveraging Notion's native sharing and permission system
- **Personal calendar integration** — starts with Google Calendar, with a clear path to support Apple Calendar (CalDAV), Outlook/Microsoft 365, and others
- **Notion as the knowledge base** — all project data, documents, and context live in Notion, connected via MCP
- **Guided onboarding** — the orchestrator walks new users through connecting Notion, setting up their calendar, and creating their first project
- **Ongoing workflow guidance** — beyond setup, the orchestrator continuously surfaces what needs attention and suggests next steps

## Installation

### Claude Code

From the chat interface, run these two commands:

```
/plugin marketplace add Erick307/PersonalProjectManager
/plugin install personal-project-manager@personal-project-manager
```

### Claude Cowork

1. Open **Customize → Plugins** in the sidebar.
2. Click **Add marketplace** and enter `Erick307/PersonalProjectManager`.
3. Find **Personal Project Manager** in the list and click **Install**.
4. Start a conversation — the assistant checks your Notion and Google Calendar connections and prompts you to connect anything missing.

## Compatibility

| Assistant | Integration method | Status |
|---|---|---|
| Claude | Skills / Plugin | Primary target |
| ChatGPT | Custom GPTs with Actions | Planned |
| Others | TBD | Future |

## Integrations

- **Notion** — project knowledge base, via Notion MCP server
- **Google Calendar** — personal scheduling layer (starting point)
- More calendars and tools to be added over time

## Status

Early stage — this README captures the vision. Implementation details will be defined as the project evolves.
