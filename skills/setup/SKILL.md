---
name: setup
description: First-time setup — connect Notion and Google Calendar to activate the Personal Project Manager. Run this before creating your first project.
effort: low
---

# Personal Project Manager — First-Time Setup

Notion and Google Calendar are both Claude's built-in connectors — this plugin does not configure or declare either one itself. Both are enabled the same way, so give the user the same instructions for each, but the correct instructions depend on where this skill is currently running:

- **Claude.ai (web), Claude Desktop, or Claude Cowork** — these have a connectors UI: **Customize → Connectors**.
- **Claude Code (CLI or IDE extension)** — there is no connectors UI here. Connectors are managed at the account level: the user must open **claude.ai or the Claude Desktop app** in a browser, go to **Customize → Connectors** there, connect it, and then it becomes available back in Claude Code automatically. Do not tell a Claude Code user to look for a "Customize" or "Settings" menu inside Claude Code itself — it doesn't have one.

Determine which surface you're running in before giving instructions.

Silently check both connections:
1. Attempt a Notion tool call (e.g., search for any page)
2. Attempt a Google Calendar tool call (e.g., list calendars)

Then report what is connected and what is not. For each one that is missing, tell the user exactly how to connect it using the correct path for the current surface (above). Keep the instructions identical in structure for both connectors so the experience stays consistent. Do not fabricate an OAuth URL — Claude generates that itself if needed once the connector is added.
