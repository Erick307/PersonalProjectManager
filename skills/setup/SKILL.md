---
name: setup
description: First-time setup — connect Notion and Google Calendar to activate the Personal Project Manager. Run this before creating your first project.
effort: low
---

# Personal Project Manager — First-Time Setup

Notion and Google Calendar are both Claude's built-in connectors (Settings → Connectors) — this plugin does not configure or declare either one itself. Both are enabled the same way, so give the user the same instructions for each.

Silently check both connections:
1. Attempt a Notion tool call (e.g., search for any page)
2. Attempt a Google Calendar tool call (e.g., list calendars)

Then report what is connected and what is not. For each one that is missing, tell the user exactly how to connect it:

1. Open Settings → Connectors (in Claude.ai, Claude Desktop, or Claude Code, depending on where they're running this).
2. Find **Notion** / **Google Calendar** in the list and click **Connect**.
3. Complete the authorization in the browser window that opens.
4. Let you know when it's done so you can re-check.

Do not fabricate an OAuth URL — Claude generates that itself if it needs to when the connector is added. Keep the instructions identical in structure for both connectors so the experience stays consistent.
