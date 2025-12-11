# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This repository contains Claude Code custom prompt configurations for a Claude + Codex collaborative workflow. There are three variants:

- `acemcp/` - Configuration with Augment MCP integration for semantic code search
- `default/` - Base configuration with detailed workflow phases
- `lite/` - Simplified configuration with minimal constraints

## File Structure

```
├── acemcp/
│   ├── CLAUDE.md    # Planner role prompt (with Augment MCP)
│   └── AGENTS.md    # Executor role prompt (with Augment MCP)
├── default/
│   ├── CLAUDE.md    # Planner role prompt (base)
│   └── AGENTS.md    # Executor role prompt (base)
├── lite/
│   ├── CLAUDE.md    # Planner role prompt (minimal)
│   └── AGENTS.md    # Executor role prompt (minimal)
└── README.md
```

## Configuration Architecture

### Role Division
- **Claude (Planner)**: Task analysis, architecture planning, solution design, documentation updates, simple code modifications
- **Codex (Executor)**: Context gathering, complex code modifications, test execution, code review

### Workflow Phases
1. **Intake** - Restate request, identify uncertainties
2. **Context Gathering** - Codex reads files, analyzes code
3. **Planning** - Design solution, use Plan Mode, require user approval
4. **Execution** - Simple tasks by Claude, complex tasks by Codex
5. **Verification** - Run tests, review changes
6. **Documentation** - Update docs (mandatory, Claude only)
7. **Handoff** - Summarize changes with file:line references

### MCP Tool Rules
- Technical API queries: context7 first, fallback to exa
- Non-technical research: exa first, fallback to web search
- `fetch`: Only for known URLs from other tools
- External dependencies: Mandatory MCP search (never hallucinate)

### Key Differences Between Variants
| Feature | `acemcp/` | `default/` | `lite/` |
|---------|-----------|------------|---------|
| Workflow definition | 7 phases | 7 phases | 4 checkpoints |
| Augment MCP integration | Yes | No | No |
| Detailed fallback/session rules | Yes | Yes | No |
| Challenge protocol | Detailed | Detailed | Minimal |
| Token footprint | Highest | Medium | Lowest |

## Editing Guidelines

- All prompt files use XML format with semantic tags
- Maintain parallel structure between variants where applicable
- `lite/` intentionally omits detailed rules—do not add complexity back
- User-facing messages must be in Simplified Chinese
- Codex communication must be in English
- Follow KISS/YAGNI principles
