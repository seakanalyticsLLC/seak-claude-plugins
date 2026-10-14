# seak-claude-plugins

Claude Code plugins for Seak Analytics client engagements.

## Plugins

- **seak-client-work** — working rules for Claude Code on a client's repo or machine: take a brief, work items on branches with PRs (never merged), keep client repos free of Seak/personal material, and report status back as comments in the client's work tracker.

This repo intentionally contains **no client information** and no references to Seak's own storage. It's safe to install on a client's machine.

## Install (once per machine)

Installs at **user scope**: recorded in that machine's user settings, nothing is written to any repository.

```bash
claude plugin marketplace add seakanalyticsLLC/seak-claude-plugins
claude plugin install seak-client-work@seak-analytics
```

The repo is private, so the machine needs read access to it (signed-in `gh`/git credentials or a fine-grained token with read-only access to this repo). Making the repo public removes that requirement.

## Update

```bash
claude plugin marketplace update seak-analytics
```

## Use

Paste a brief into a Claude Code session in the client repo and say "work this brief". The `client-brief` skill loads automatically for client work; you can also invoke it directly as `/seak-client-work:client-brief`.
