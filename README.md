# seak-claude-plugins

Claude Code plugins for Seak Analytics client engagements.

## Plugins

- **seak-client-work** — working rules for Claude Code on a client's repo or machine: pick up a brief from the client's tracker, work items on branches with PRs (never merged), keep client repos free of Seak/personal material, and report status back as comments in the client's work tracker.

This repo intentionally contains **no client information** and no references to Seak's own storage. It's safe to install on a client's machine.

## Install (once per machine)

VS Code extension: type `/plugins` in the Claude Code panel → **Marketplaces** → add `seakanalyticsLLC/seak-claude-plugins` → **Plugins** → **seak-client-work** → **Install** → **Install for you** (user scope; never "for this project", which writes to the repo).

CLI:

```bash
claude plugin marketplace add seakanalyticsLLC/seak-claude-plugins
claude plugin install seak-client-work@seak-analytics
```

## Update

VS Code: `/plugins` → **Marketplaces** → refresh icon on `seak-analytics`. CLI: `claude plugin marketplace update seak-analytics`.

## Use

In a Claude Code session in the client repo: "work the brief on #<parent work item>". The `client-brief` skill finds the newest `Brief for Claude Code` comment on that item. You can also paste a brief, or invoke the skill directly as `/seak-client-work:client-brief`.
