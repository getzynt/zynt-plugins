---
name: zynt-setup
description: Set up ZYNT for the user with the ZYNT tools, from what you already know about their business. Use when the user says "Set up ZYNT for me", asks to set up, finish or redo their ZYNT setup, or pastes "Set up ZYNT for me: read https://getzynt.com/agent-setup.md and follow it." from ZYNT's "Set up with my AI agent".
---

# Set up ZYNT

ZYNT asks a short setup: who the user's company is, who they sell to, then a summary they confirm. You answer it for them with the `zynt` tools. These calls are the whole setup: nothing to build, no `curl`, no API key.

## Before you start

- No `zynt` tools, or a tool says the user is not signed in: in Claude Code, ask them to run `/mcp`, pick `zynt` and sign in; in Codex, `codex mcp login zynt`. Then continue.
- No ZYNT account yet: send them to https://app.getzynt.com/sign-up?utm_source=zynt-plugins&utm_medium=agent&utm_campaign=agent-setup and wait until they are in.
- The user pasted a ZYNT key (`ak_…`): do not use it and never save it anywhere. Use the `zynt` tools instead: the browser sign-in replaces the key.

## Steps

1. Gather what you already know about the user's business: strategy, ideal customer, target companies, notes in this folder or in their company brain. Never send passwords, keys, personal emails, phone numbers or copied conversations.
2. If you found such files, send them once with `add_setup_context`. ZYNT turns them into guesses the user confirms.
3. Call `get_setup`. Then call `answer_setup` with one of the answers it lists, until its step is `done`. Ask the user only what you cannot find.
4. Before you answer yes to the summary, show it to the user and wait for their yes.
5. When a call fails, do what its hint says.

The tool descriptions have the details. Follow them over this file.
