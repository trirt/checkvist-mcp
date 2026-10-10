
# Checkvist plugin for Codex, Claude Code, and Gemini CLI

[Checkvist](https://checkvist.com) is a keyboard-first outliner where notes, tasks, 
and plans live in the same deeply nested lists.

Use the Checkvist plugin to let your coding assistant read and search your lists
via [MCP server](https://checkvist.com/help/mcp).

Save summaries, action items, and task lists directly to Checkvist.
You choose whether your coding assistant gets read-only or write access.

## Install

### Claude Code

In the command line, run
```
claude plugin marketplace add trirt/checkvist-claude-plugin
claude plugin install checkvist@checkvist
```

Then run `/mcp` in the claude code and authenticate. The server speaks OAuth, so there is no API token to paste —
and you can grant read-only access if you prefer. Connected apps are listed on your
[Profile → Tools](https://checkvist.com/auth/profile#tools) page and can be disconnected there.

### Gemini CLI

The same repository is also a Gemini CLI extension:
```
gemini extensions install https://github.com/trirt/checkvist-claude-plugin
```

Gemini CLI opens the browser for OAuth on the first connection.

### Codex

For local development, expose this folder through your personal Codex marketplace:

```bash
mkdir -p ~/plugins
ln -sfn "$(pwd)" ~/plugins/checkvist
```

Create or update `~/.agents/plugins/marketplace.json`, preserving any existing plugin
entries, with this Checkvist entry:

```json
{
  "name": "personal",
  "interface": { "displayName": "Personal" },
  "plugins": [
    {
      "name": "checkvist",
      "source": { "source": "local", "path": "./plugins/checkvist" },
      "policy": {
        "installation": "AVAILABLE",
        "authentication": "ON_INSTALL"
      },
      "category": "Productivity"
    }
  ]
}
```

Then install the plugin:

```bash
codex plugin add checkvist@personal
```

Start a new Codex thread so the Checkvist MCP tools are loaded, then complete the
browser-based OAuth flow when prompted.


## What you can ask for

- Create a new list from the conversation summary
- Summarize a list
- Find some information in your lists, use #tags for search
- Ask for current due tasks
- Add a batch of items at once, with indentation creating the hierarchy
- Export a list as markdown or OPML

## License

MIT
