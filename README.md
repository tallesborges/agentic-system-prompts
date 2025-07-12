# AI Agent System Prompts Library

[![GitHub stars](https://img.shields.io/github/stars/tallesborges/agentic-system-prompts?style=flat-square)](https://github.com/tallesborges/agentic-system-prompts/stargazers)
[![GitHub license](https://img.shields.io/github/license/tallesborges/agentic-system-prompts?style=flat-square)](https://github.com/tallesborges/agentic-system-prompts/blob/main/LICENSE)
[![GitHub last commit](https://img.shields.io/github/last-commit/tallesborges/agentic-system-prompts?style=flat-square)](https://github.com/tallesborges/agentic-system-prompts/commits/main)

A curated collection of system prompts and tool definitions from production AI coding agents, extracted and documented for research and educational purposes.

## Table of Contents

- [Agent Comparison](#agent-comparison)
- [What's Included](#whats-included)
- [Research Value](#research-value)
- [Contributing](#contributing)
- [License](#license)

## Agent Comparison

| Agent | Provider | Type | Tools | Key Features |
|-------|----------|------|-------|-------------|
| [Claude Code](./agents/claude-code/) | Anthropic | CLI | 16 | Task management, web search, comprehensive file ops |
| [Gemini CLI](./agents/gemini-cli/) | Google | CLI | 11 | Memory management, multi-file reading, web capabilities |
| [Cline](./agents/cline/) | Open Source | VS Code | 12 | MCP support, browser integration, planning mode |
| [Aider](./agents/aider/) | Open Source | CLI | Git-based | Multiple edit modes, git integration |
| [Roo Code](./agents/roo-code/) | RooCode Inc | VS Code | 12 | Dynamic prompts, mode switching, comprehensive workflow |
| [Zed](./agents/zed/) | Zed Industries | Editor | 15 | Editor integration, diagnostics, thinking tool |
| [Codex CLI (TypeScript)](./agents/codex-cli/) | OpenAI | CLI | Function calls | Natural language codebase interaction |
| [Codex CLI (Rust)](./agents/codex-rs/) | OpenAI | CLI | 1 | Rust CLI with patch-based editing |

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
