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

1. Call `get_setup` first. It says where the setup stands and the answers it takes now.
2. While the setup is still at its first questions (step `company` or `customers`), send what you know about the user's business once with `add_setup_context`: strategy, ideal customer, target companies, the list of current customers, notes in this folder or in their company brain. Send business facts only: never passwords, keys, personal emails, other people's phone numbers, deal amounts or copied conversations. ZYNT turns the files into guesses the user confirms. If it refuses, do what its hint says and go on without it.
3. Call `answer_setup` with one of the answers `get_setup` lists, until its step is `done`. Ask the user only what you cannot find. ZYNT asks for a phone number: tell the user it calls only if the setup gets stuck.
4. Before you answer yes to the summary, show it to the user and wait for their yes.
5. When a call fails, do what its hint says. No setup open means the workspace is set up already: say so, and help with the user's news instead (the `zynt-news` skill).
6. When the step is `done`, tell the user: ZYNT now reads the news about the companies on their lists. The news shows at once; signals, the news that gives them a reason to talk to a company now, can take a while. Offer to show the news ("Signals for me").

The tool descriptions have the details. Follow them over this file.
