<img src="logo.svg" alt="Checkvist" width="72" align="left" hspace="12">

# Checkvist plugin for Claude Code

[Checkvist](https://checkvist.com) is a keyboard-first outliner where notes, tasks, 
and plans live in the same deeply nested lists.

Use the Checkvist plugin to let Claude Code read and search your lists 
via [MCP server](https://checkvist.com/help/mcp).

Save summaries, action items, and task lists directly to Checkvist. 
You choose whether Claude Code gets read-only or write access.

## Install

```
/plugin marketplace add trirt/checkvist-claude-plugin
/plugin install checkvist@checkvist
```

Then run `/mcp` and authenticate. The server speaks OAuth, so there is no API token to paste —
and you can grant read-only access if you prefer. Connected apps are listed on your
[Profile → Tools](https://checkvist.com/auth/profile#tools) page and can be disconnected there.

## What you can ask for

- Create a new list from the conversation summary
- Summarize a list
- Find some information in your lists, use #tags for search
- Ask for current due tasks
- Add a batch of items at once, with indentation creating the hierarchy
- Export a list as markdown or OPML

## License

MIT
