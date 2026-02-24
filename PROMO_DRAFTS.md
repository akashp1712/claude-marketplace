# Crux Promotional and Publishing Materials

Here are drafted materials for you to copy and paste to get the word out about your new Claude Code plugin!

***

### 1. Reddit Post (r/ClaudeAI & r/Anthropic)
**Title:** I built a local plugin for Claude Code that fixes Context Compaction (Crux)
**Body:**
> Hey everyone, 
> 
> I've been using Claude Code daily, but I kept running into an issue with long sessions: **context compaction**. I’d give Claude a hard constraint (e.g. "We only use REST, absolutely no GraphQL"), and 40 turns later after compaction, it would suggest GraphQL again. It remembered the decision, but forgot *why* it mattered.
>
> To fix this, I built **Crux** — a local, zero-dependency plugin for Claude Code.
>
> 🧠 **What it does:** 
> Every memory tool right now (cursor memory, claude.md) stores flat facts. Crux stores decisions as **causal triples**: `CONSTRAINT -> RATIONALE -> DECISION`.
> It hooks directly into the Claude Code lifecycle and actively injects co-inclusion rules right before compaction happens. It literally forbids Claude from separating a decision from its rationale. 
>
> ⚙️ **Installation:**
> It uses the native plugin system. Just run:
> ```bash
> /plugin marketplace add akashp1712/claude-marketplace
> /plugin install crux@akashp1712
> ```
> 
> 🔗 Source code and architecture details are on GitHub: https://github.com/akashp1712/claude-crux
> 
> Would love for folks to try it and give feedback! It runs locally but has hybrid API fallbacks for complex extractions. 

***

### 2. X (Twitter) Thread
**Tweet 1:**
Claude Code is amazing, until context compaction ruins your hard constraints. 

Tell it "Use REST, no GraphQL" -> 40 turns later, it suggests GraphQL again. 

I got tired of this, so I built Crux: a native Claude Code plugin that remembers the *WHY* behind decisions. 🧠🧵👇

**Tweet 2:**
Traditional memory tools (CLAUDE.md, Cursor rules) store flat facts. Claude sees it as a "suggestion" and overrides it. 

Crux hooks into the Claude Code lifecycle and stores decisions as causal triples (Constraint -> Rationale -> Decision).

**Tweet 3:**
Right before Claude compacts context, Crux dynamically injects instructions forbidding it from separating your decision from your rationale.

Installation is native and takes 2 seconds:
`/plugin marketplace add akashp1712/claude-marketplace`
`/plugin install crux@akashp1712`

**Tweet 4:**
It's zero-dependency, open-source, and has hybrid local/API extraction modes. 

Check out the repo and the architecture graph here: https://github.com/akashp1712/claude-crux

Feedback welcome! #ClaudeCode #Anthropic #AI #DevTools

***

### 3. GitHub "Awesome Lists" Pull Request Description
*(Use this PR description when submitting to repos like `hesreallyhim/awesome-claude-code`, `jqueryscript/awesome-claude-code`, or `xbim08/awesome-claude-code-plugins`)*

**Title:** Add `Crux` - A context compaction and memory plugin
**Body:**
> Adds **Crux** to the Plugins section.
>
> **Description:** Crux is a native Claude Code plugin that solves context compaction amnesia. It extracts developer decisions into causal triples (Constraint -> Rationale -> Decision) and automatically injects pre-compaction prompts to ensure Claude never separates a decision from its foundational reasoning.
> 
> **Link:** https://github.com/akashp1712/claude-crux
> **Marketplace Install:** `/plugin marketplace add akashp1712/claude-marketplace`

***

### 4. Claude Code Commands Directory Submission
*(For sites like claudemarketplaces.com or claudecodecommands.directory)*

**Name:** Crux Memory Engine
**Description:** A plugin that fixes context compaction amnesia in Claude Code. It stores your decisions as causal triples and actively hooks into the pre-compaction lifecycle to ensure Claude always remembers the 'why' behind your rules.
**Installation Command:** `/plugin marketplace add akashp1712/claude-marketplace && /plugin install crux@akashp1712`
**Repository:** https://github.com/akashp1712/claude-crux
**Tags:** Memory, Context, Plugin, Developer Tools
