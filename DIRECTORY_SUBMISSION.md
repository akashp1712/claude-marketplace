---
description: Install Crux - Solves Context Compaction with a Causal Graph
category: productivity
---

# Crux - Context Compaction Immunity for Claude Code

Crux enhances Claude Code by solving the biggest problem with long conversational context: **Context Compaction Amnesia**. It actively hooks into Claude Code's lifecycle to ensure decisions and their rationales are never separated during summarization. 

## Installation

```bash
# 1. Add the marketplace
/plugin marketplace add akashp1712/claude-marketplace

# 2. Install the plugin
/plugin install crux@akashp1712
```

## Features

- **Causal Memory Graph**: Decisions are stored as causal triples (`CONSTRAINT -> RATIONALE -> DECISION`), not flat facts.
- **Compaction Immunity**: Injects strict co-inclusion rules right before Claude compacts context, forbidding it from separating reasoning from decisions.
- **Auto-Extraction**: Understands and extracts decisions naturally from the conversation without needing manual commands.
- **Zero Configuration**: Runs inherently as a native Claude Code plugin with zero NPM dependencies.
- **Session-Scoped Clean Slate**: Decisions don't permanently leak. Start a new session, get a clean slate. Promote to `CLAUDE.md` only when desired.

## Commands Available

After installation, Crux provides these slash commands:

- `/crux:status` - Inspect the current session's active decision graph
- `/crux:export` - Persist active session decisions to your permanent `CLAUDE.md`

## Example Usage

With Crux installed, if you say:
_"Use REST not GraphQL — our team only knows REST."_

Forty turns later, instead of Claude overriding this constraint because it forgot the "why", Crux's PreCompact hook ensures Claude still knows that REST is a rigid constraint based on team skills. 

## Requirements

- Claude Code CLI (latest version)
- Node.js >= 18.0.0

## Documentation

- **Repository**: https://github.com/akashp1712/claude-crux
- **Marketplace Hub**: https://github.com/akashp1712/claude-marketplace

## Architecture & Privacy

- **100% Local (by default)**: Uses a regex engine locally, with an optional hybrid Anthropic API extraction mode (`CRUX_EXTRACTION_MODE`).
- **Native Hooks**: Hooks directly into `UserPromptSubmit` and `PreCompact` plugin lifecycle events.
- Open source (MIT)

---

**Note**: Crux is a native **Claude Code Plugin**, installed directly via the `/plugin marketplace` system. It manages memory invisibly during the conversation.
