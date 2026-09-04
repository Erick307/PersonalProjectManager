---
name: setup
description: First-time setup — connect Notion and Google Calendar to activate the Personal Project Manager. Run this before creating your first project.
effort: medium
maxTurns: 20
---

# Personal Project Manager — First-Time Setup

You are running the first-time setup for the Personal Project Manager. Your job is to get Notion and Google Calendar connected. Work through the steps in order, one at a time. Be concise — the user does not need long explanations at each step.

## Before You Start

Silently verify both connections before saying anything:
1. Attempt a Notion tool call (e.g., search for any page)
2. Attempt a Google Calendar tool call (e.g., list calendars)

Use the results to determine which steps to skip.

## Step 1: Welcome

Greet the user briefly. Tell them setup connects two things:
- Notion — where their projects will live
- Google Calendar — for scheduling and time management

If both are already connected, tell them that, skip to Step 4.

## Step 2: Connect Notion

If Notion tools are available and working, tell the user Notion is already connected. Skip to Step 3.

If not:

Tell the user Notion connects via a quick OAuth login — no API keys needed. Ask them to run this command in their terminal:

```
claude mcp add --transport http notion https://mcp.notion.com/mcp
```

Tell them a browser window will open to log into Notion and approve access. Ask them to complete that and come back to confirm.

Once they confirm, silently attempt a Notion tool call to verify. If it works, move on. If not, help them troubleshoot: confirm the command ran, the browser opened, and approval was completed.

## Step 3: Connect Google Calendar

If Google Calendar tools are available and working, tell the user it is already connected. Skip to Step 4.

If not:

Tell the user Google Calendar connects through Claude's connectors. Walk them through:
1. Open Claude settings
2. Go to Connectors
3. Find Google Calendar and click Connect
4. Log in with their Google account and approve access

Ask them to confirm when done, then silently verify with a calendar tool call. If it fails, ask if they completed the approval step in the browser.

## Step 4: Done

Confirm what is now connected:
- Notion: connected
- Google Calendar: connected

Tell the user their Personal Project Manager is ready. Ask if they would like to create their first project now.
