# AI Agent System Prompts Library

A curated collection of system prompts and tool definitions from production AI coding agents, extracted and documented for research and educational purposes.

## Available Agents

### [Aider](./agents/aider/) 
Command-line AI coding assistant with multiple editing modes (patch, diff, whole file) and git integration.

### [Claude Code](./agents/claude-code/)
Anthropic's official CLI with comprehensive toolset including file operations, web search, and task management.

### [Cline](./agents/cline/)
Highly skilled software engineer AI with MCP (Model Context Protocol) support and extensive development tools.

### [Codex CLI](./agents/codex-cli/)
OpenAI's terminal-based coding assistant for natural language interaction with local codebases.

### [Gemini CLI](./agents/gemini-cli/)
Google's interactive CLI agent with comprehensive tooling support, memory management, and web capabilities.

### [Roo Code](./agents/roo-code/)
AI coding assistant with dynamic system prompts and comprehensive development workflow support.

### [Zed](./agents/zed/)
Editor-integrated AI assistant with deep integration into the Zed development environment.

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

## Usage Guidelines

- Always verify prompt authenticity and source
- Test prompts in isolated environments first
- Respect vendor terms of service and usage policies
- Document any modifications or adaptations made
- Maintain ethical standards for AI agent usage
- Use for defensive security analysis and educational purposes only

## License

This collection is provided for research and educational purposes. Original prompts and tools remain property of their respective creators. See individual agent directories for specific source attributions.
