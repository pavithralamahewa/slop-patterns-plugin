# Slop Patterns plugin

Checks the UI code your AI writes for AI-default design patterns, like the gradient headline, the badge above the hero and three identical feature cards, and gives the fix for each. Uses the open [Slop Patterns](https://sloppatterns.com) library.

Contents:
- `.mcp.json`: the Slop Patterns MCP server (`https://sloppatterns.com/mcp`, no account or key)
- `skills/check-ui/SKILL.md`: check UI before showing it, apply the fixes, re-check
- `rules/slop-patterns.mdc`: the same workflow as a Cursor rule

## Install

**Claude Code:** `/plugin marketplace add pavithralamahewa/slop-patterns` then `/plugin install slop-patterns@slop-patterns`

**Cursor:** add the MCP server (Settings → MCP, type HTTP, URL above) and copy `rules/slop-patterns.mdc` into `.cursor/rules/`.

## Privacy
Code sent to `check_design` is checked and discarded, never stored or used for training. See https://sloppatterns.com/privacy

By Pavithra Lamahewa at [Precious Studio](https://precious.studio). MIT license.
