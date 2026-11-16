# Install the ZYNT plugin

Instructions for an AI agent. Follow them in order and do nothing else in this repository.

The plugin connects you to ZYNT's remote MCP server, `https://app.getzynt.com/mcp`, and adds two skills: `zynt-setup` and `zynt-news`. The user signs in once with their ZYNT account in the browser. There is no API key to paste or store, and nothing runs on the user's machine.

## Codex

1. Run `codex plugin marketplace add getzynt/zynt-plugins`.
2. Run `codex plugin add zynt@zynt`.
3. Run `codex mcp login zynt`. It opens the browser: ask the user to sign in to ZYNT and approve access. Wait until the command ends.
4. Tell the user to start a new chat so the ZYNT tools load, and to say "Set up ZYNT for me" there.

## Claude Code

1. Tell the user to type these two commands in Claude Code, one after the other (you cannot run slash commands yourself):
   - `/plugin marketplace add getzynt/zynt-plugins`
   - `/plugin install zynt@zynt`
2. Then: `/mcp`, pick `zynt`, and sign in to ZYNT in the browser.
3. Then: say "Set up ZYNT for me".

## No ZYNT account yet

Send the user to https://app.getzynt.com/sign-up?utm_source=zynt-plugins&utm_medium=agent&utm_campaign=agent-setup first.

## Claude.ai and ChatGPT

They have no plugins. Add ZYNT there as a custom connector with the URL `https://app.getzynt.com/mcp`: https://app.getzynt.com/docs#mcp
