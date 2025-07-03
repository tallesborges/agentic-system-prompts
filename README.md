# Agentic System Prompts Library

A comprehensive collection of system prompts and tools used by AI coding agents like Claude Code, Gemini CLI, GitHub Copilot, Codex, and others.

## Project Structure

```
/
├── agents/                    # System prompts organized by agent
│   ├── claude-code/
│   │   └── system-prompt.md
│   ├── codex/
│   │   └── system-prompt.md
│   └── gemini-cli/
│       └── system-prompt.md
├── docs/                      # Documentation and guides
└── scripts/                   # Automation and validation tools
    ├── validators/
    └── fetchers/
```

## Agent Categories

### Code Generation Agents
- **Claude Code** - Anthropic's CLI coding assistant
- **Codex** - OpenAI's code generation model
- **Gemini CLI** - Google's command-line coding agent

### Analysis Agents
- Security auditing agents
- Code review agents
- Performance analysis agents

### Specialized Agents
- Documentation generators
- Test generators
- Refactoring assistants

## Data Sources

Prompts are collected from various sources:
- **Official Documentation** - Vendor-published specifications
- **Community Observation** - Reverse-engineered from interactions
- **Research Papers** - Academic publications
- **Tool Analysis** - Direct inspection of agent behavior

## Future Plans

- **Automated Fetching** - Scripts to automatically update prompts from various sources
- **Version Tracking** - Change detection and update notifications
- **Comparison Tools** - Side-by-side analysis of different agents
- **Usage Analytics** - Track which prompts and patterns are most effective

## Contributing

1. Create a new directory under the appropriate agent path
2. Add a `system-prompt.md` file with the complete system prompt
3. Include source information and retrieval date in the prompt header
4. Follow the contribution guidelines in `docs/CONTRIBUTING.md`

## Usage Guidelines

- Always verify prompt authenticity and source
- Test prompts in isolated environments first
- Respect vendor terms of service and usage policies
- Document any modifications or adaptations made
- Maintain ethical standards for AI agent usage
