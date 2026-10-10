# Checkvist MCP plugin for Codex, Claude Code, and Gemini CLI

[Checkvist](https://checkvist.com) is a keyboard-first outliner where notes, tasks, 
and plans live in the same deeply nested lists.

Use the Checkvist plugin to let your coding assistant read and search your lists
via [MCP server](https://checkvist.com/help/mcp).

Save summaries, action items, and task lists directly to Checkvist.
You choose whether your coding assistant gets read-only or write access.

This repository packages the [Checkvist MCP server](https://checkvist.com/mcp); 
the server itself runs on checkvist.com.

## Authentication

All three hosts use the same flow: the server speaks OAuth, so there is no API token to
paste, and you can grant read-only access if you prefer. Your assistant opens a browser
on the first connection. Connected apps are listed on your
[Profile → Tools](https://checkvist.com/auth/profile#tools) page and can be disconnected
there.

## Install

### Claude Code

```bash
claude plugin marketplace add trirt/checkvist-mcp
claude plugin install checkvist@checkvist
```

Then run `/mcp` in Claude Code and authenticate.

### Gemini CLI

```bash
gemini extensions install https://github.com/trirt/checkvist-mcp
```

### Codex

```bash
codex plugin marketplace add trirt/checkvist-mcp
codex plugin add checkvist@checkvist
```

Start a new Codex thread so the Checkvist MCP tools are loaded.

## What you can ask for

- Create a new list from the conversation summary
- Summarize a list
- Find some information in your lists, use #tags for search
- Ask for current due tasks
- Add a batch of items at once, with indentation creating the hierarchy
- Export a list as markdown or OPML

## License

MIT
