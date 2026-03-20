# Presentation Builder

This file enables the presentation skill for AI IDEs that support AGENTS.md (Claude Code, Codex, and others).

## Instructions

Read and follow the full instructions in [SKILL.md](SKILL.md) in this directory. That file contains the complete workflow for generating interactive HTML slide deck presentations.

The HTML template is at [template.html](template.html) and the slide component library is at [components.md](components.md) in this directory.

## Quick Summary

1. Ask the user: what topic, what goal, who is the audience
2. Research: gather context from GitHub issues, PRs, docs, data
3. Outline: propose 8-14 slides with types from the component library
4. Generate: build the HTML deck using the template (CSS/JS verbatim)
5. Save and offer to refine
