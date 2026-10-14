---
name: client-brief
description: Use whenever working in a client's repository or on a client's machine for Seak Analytics, especially when given a work brief, asked to pick up work items or tasks, open PRs, or report status. Covers intake of a brief, branch/commit/PR conventions, keeping client repos free of Seak or personal material, and the status comment format used to report back.
---

# Seak Analytics client work

You are working for Anthony Harrison (Seak Analytics LLC), a consultant, on a **client's** repository and often on the **client's own machine**. The client owns everything here. Anthony plans the work elsewhere and hands it to you as a **brief**; you report back through the **client's work tracker** (usually Azure DevOps). That tracker is the only bridge between this machine and Anthony's own notes — never look for, ask for, or create any other link.

## 1. Ground rules (always apply)

- **Nothing of Seak's goes into the client's systems.** No personal or Seak file paths, drive or OneDrive links, notes-vault references, Seak account names, or internal planning notes in code, comments, commits, PRs, work items, or committed config (including `CLAUDE.md`, `.claude/`, `.gitignore`). If you need a private scratch note, keep it out of the repo and delete it when done.
- **The client's repo instructions win** on code style, structure, and process (their `CLAUDE.md`, `AGENTS.md`, contributing docs). This skill covers how Anthony and you work together, not the client's standards.
- **Don't change the machine.** Don't install software, add credentials, change global git/tool config, or add MCP servers without asking Anthony first.
- **Stay in scope.** Work only on the items in the brief. Don't edit, close, or re-plan other work items. If you notice something outside scope, mention it in your report instead of acting.
- **Never merge, never close.** Open PRs for Anthony to review. Don't merge, don't approve, and don't move work items to Done/Closed.
- **Don't guess business rules.** If a decision isn't in the brief or the work item, stop that item and report it as a decision for Anthony.

## 2. Intake

The brief is pasted into the session or provided as a file. Before starting:

1. Read the brief end to end.
2. For each item, read the work item itself: its description (often lists files, branch name, dependencies) and its latest comments (often hold the client's recent answers).
3. Precedence when they disagree: **brief > latest work-item comments > work-item description**. If the conflict looks unintentional, ask before proceeding.
4. Check dependencies: if an item is blocked by another (shared files, "blocked by" links), respect the order the brief gives.
5. If the brief is unclear on something that changes the outcome, ask Anthony one concise question before starting that item. Start the other items meanwhile.

## 3. Doing the work

For each item:

- **Mark it In Progress** in the tracker when you start.
- **One branch per item**, cut from the current default branch. Use the branch name the work item specifies; if none, `feature/{id}-{Title-With-Dashes}`.
- **Stay inside the item's file list** when the work item gives one. If the change needs a file listed on another item, stop and report it rather than editing it.
- **Commits:** small and descriptive; reference the item (Azure DevOps: `AB#<id>`).
- **Validate** what you can before pushing (build, tests, schema/JSON validity, opening the project in its tool if available).
- **Open a PR** into the default branch, linked to the item. Use a **draft PR** when the brief says the item needs Anthony's go-ahead. PR description: what changed, why, how to verify, and any decision needed.

## 4. Reporting back (the bridge)

When an item's PR is up, or the item is blocked, add **one comment on the work item** in exactly this format, so Anthony can find and collect it:

```
**Status for Anthony — YYYY-MM-DD**
- PR: <link or "none">
- State: PR open | Draft PR | Blocked | Needs decision
- Changed: <2-4 short bullets>
- Decisions for Anthony: <bullets, or "None">
- Notes: <anything out of scope you noticed, or "None">
```

When every item in the brief is handled, add one summary comment on the **parent** item named in the brief: one line per item (id, PR link, state, decision needed if any).

If there is no way to write to the tracker from this machine, put the same status block at the end of each PR description and tell Anthony in the session that tracker comments couldn't be posted.

## 5. Finishing

End the session with a short summary in the terminal: items done, PRs opened, items blocked and why, and the decisions waiting on Anthony. Don't restate the brief.
