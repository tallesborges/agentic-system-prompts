# Contributing to AI Agent System Prompts Library

Thank you for your interest in contributing! This guide will help you add new agent prompts and tools to the collection.

## How to Contribute

### Adding a New Agent

1. **Create Agent Directory**
   ```bash
   mkdir agents/[agent-name]
   mkdir agents/[agent-name]/tools  # if agent has tools
   ```

2. **Add System Prompt**
   Create `agents/[agent-name]/system-prompt.md` following this template:
   ```markdown
   # [Agent Name] System Prompt

   **Source:** [Direct URL to source]
   **Location:** [Specific function/file/API endpoint]
   **Retrieved:** [YYYY-MM-DD]

   ---

   [Complete system prompt with dynamic placeholders]
   ```

3. **Document Tools** (if applicable)
   For each tool, create `agents/[agent-name]/tools/[ToolName].md`:
   ```markdown
   # [Tool Name] Tool

   **Source:** [Direct URL to source]
   **Location:** [Specific function/file/API endpoint]
   **Retrieved:** [YYYY-MM-DD]

   ---

   ## Description

   [Exact original tool description from API]

   ## Input Schema

   ```json
   [Original JSON schema from API]
   ```
   ```

4. **Create Agent README**
   Add `agents/[agent-name]/README.md` with overview and file listings.

### Quality Standards

**System Prompts Must Include:**
- [ ] Complete prompt with all conditional sections
- [ ] Dynamic placeholders documented
- [ ] Verifiable source URL
- [ ] Extraction method explained
- [ ] Proper template format

**Tool Documentation Must Include:**
- [ ] Original tool description (unmodified)
- [ ] Complete JSON schema from source
- [ ] All usage notes and examples
- [ ] Parameter requirements documented
- [ ] Source attribution complete

### Discovery Methods

**Preferred Sources (in reliability order):**
1. **Public Source Code** - GitHub/GitLab repositories
2. **Official Documentation** - API docs, technical specifications
3. **Network Analysis** - API request inspection (research only)
4. **Application Analysis** - Configuration files, reverse engineering

**Search Patterns:**
- Prompts: `prompt`, `system_message`, `instructions`, `getCoreSystemPrompt()`
- Tools: `tools`, `functions`, `input_schema`, `description`
- Files: `prompts.ts`, `prompts.py`, `main.py`, `cli.py`, `constants.py`

### Content Guidelines

**What to Document:**
- Complete system prompts as sent to AI models
- All available tools with full API specifications
- Conditional logic and dynamic components
- Examples and usage patterns

**What NOT to Include:**
- Modified or interpreted prompts
- Incomplete tool definitions
- Speculative or reconstructed content
- Proprietary or sensitive information

### Testing Your Contribution

Before submitting:
1. Verify all URLs are accessible
2. Check that prompts are complete and formatted correctly
3. Ensure proper source attribution
4. Test that all links work
5. Follow the established naming conventions

### Submission Process

1. Fork the repository
2. Create a feature branch: `git checkout -b add-[agent-name]`
3. Add your agent following the guidelines above
4. Update the main README.md to include your agent
5. Submit a pull request with:
   - Clear description of the agent
   - Source verification
   - Quality checklist completion

### Examples of Good Contributions

See existing agents for reference:
- [Claude Code](./agents/claude-code/) - Complete tool documentation
- [Gemini CLI](./agents/gemini-cli/) - Comprehensive prompt extraction
- [Cline](./agents/cline/) - MCP tool integration example

## Questions?

- Open an issue for questions about specific agents
- Check existing issues before creating new ones
- Reach out for guidance on complex extractions

We appreciate your contributions to this research resource!