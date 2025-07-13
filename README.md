# AI Agent System Prompts Library

[![GitHub stars](https://img.shields.io/github/stars/tallesborges/agentic-system-prompts?style=flat-square)](https://github.com/tallesborges/agentic-system-prompts/stargazers)
[![GitHub license](https://img.shields.io/github/license/tallesborges/agentic-system-prompts?style=flat-square)](https://github.com/tallesborges/agentic-system-prompts/blob/main/LICENSE)
[![GitHub last commit](https://img.shields.io/github/last-commit/tallesborges/agentic-system-prompts?style=flat-square)](https://github.com/tallesborges/agentic-system-prompts/commits/main)

What are the differences between agentic coding tools? TBH, most of the differences are the system prompts and the tools they provide, as well as how they handle them. In this repo, I would like to document these system prompts and the tools provided by these agentic coding tools.

## Table of Contents

- [Agent Comparison](#agent-comparison)
- [What's Included](#whats-included)
- [Research Value](#research-value)
- [Contributing](#contributing)
- [License](#license)

## Agent Comparison

| Agent | Provider | Type | Tools |
|-------|----------|------|-------|
| [Claude Code](./agents/claude-code/) | Anthropic | CLI | 16 |
| [Gemini CLI](./agents/gemini-cli/) | Google | CLI | 11 |
| [Cline](./agents/cline/) | Open Source | VS Code | 12 |
| [Aider](./agents/aider/) | Open Source | CLI | Git-based |
| [Roo Code](./agents/roo-code/) | RooCode Inc | VS Code | 12 |
| [Zed](./agents/zed/) | Zed Industries | Editor | 15 |
| [Codex CLI (Rust)](./agents/codex-rs/) | OpenAI | CLI | 1 |

## What's Included

Each agent directory contains:
- **System Prompts** - Complete prompt templates with role definitions and instructions
- **Tool Documentation** - Detailed API specifications for all available tools
- **Source Attribution** - Direct links to original sources with retrieval dates
- **README** - Overview with GitHub repository links and feature summaries

## Research Value

This collection provides insights into:
- **Prompt Engineering Patterns** - How production systems structure AI instructions
- **Tool Design** - Common patterns in AI agent tooling and capabilities
- **Safety Measures** - Security considerations and defensive programming practices
- **User Experience** - How different agents handle interaction and workflow management

## Contributing

1. Create a new directory under `agents/[agent-name]/`
2. Add a `system-prompt.md` file with the complete system prompt
3. Document tools in `agents/[agent-name]/tools/` directory
4. Include source information and retrieval date in headers
5. Follow the established template formats (see [CLAUDE.md](./CLAUDE.md))

## Roadmap

Planned additions to this repository:

- [ ] **Tools Comparison** - Detailed analysis and comparison of tools across different agents
- [ ] **Prompts Analysis** - In-depth analysis of prompt engineering patterns and techniques

## License

This collection is provided for research and educational purposes. Original prompts and tools remain property of their respective creators. See individual agent directories for specific source attributions.
