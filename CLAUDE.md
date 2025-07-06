# AI Agent System Prompts Library - Claude Code Guidelines

## Project Overview

This repository is a curated library of AI agent system prompts extracted from production systems. The goal is to document complete prompt templates as they would be sent to AI models.

## Claude Code Workflow Guidelines

### Core Principles

1. **Quality Over Quantity** - Focus on complete, well-documented prompts
2. **Evidence-Based** - All prompts must have verifiable source attribution
3. **Completeness** - Capture full system prompts including dynamic parts and conditional logic

### Working with This Project

**File Structure**
- Agent prompts: `agents/[agent-name]/system-prompt.md`
- Use kebab-case naming (e.g., `claude-code`, `gemini-cli`)

**Standard Template Format**
```markdown
# [Agent Name] System Prompt

**Source:** [Direct URL to source]
**Location:** [Specific function/file/API endpoint]
**Retrieved:** [YYYY-MM-DD]

---

[Complete system prompt with dynamic placeholders]
```

### Discovery & Extraction Methods

**Primary Sources (in order of reliability)**
1. **Public Source Code** - GitHub/GitLab repositories
2. **Official Documentation** - API docs, technical blogs
3. **Network Analysis** - API request inspection (research only)
4. **Application Analysis** - Reverse engineering, config files

**Key Search Patterns**
- Keywords: `prompt`, `system_message`, `instructions`, `getCoreSystemPrompt()`
- Common files: `prompts.ts`, `prompts.py`, `main.py`, `cli.py`, `constants.py`

### Tool Usage for This Project

**Essential Tools**
- `WebFetch` - Retrieve files from URLs
- `Grep/Glob` - Search for prompt patterns
- `Bash` with `curl` - Direct file retrieval
- `Task` - Complex multi-step searches

**Common Commands**
```bash
# GitHub raw file access
curl -s "https://raw.githubusercontent.com/[owner]/[repo]/[branch]/path/to/file"

# Search for prompt functions
rg "getCoreSystemPrompt|getSystemPrompt|buildPrompt"
```

### Prompt Analysis Requirements

**What to Document**
- **Static Components** - Core instructions, personality guidelines
- **Dynamic Components** - Template variables, environment-specific sections
- **Conditional Logic** - Platform-specific instructions, feature toggles
- **Examples** - Interaction patterns, tool usage demonstrations

**Quality Checklist**
- [ ] All conditional sections included
- [ ] Dynamic placeholders documented
- [ ] Source URL accessible and specific
- [ ] Extraction method documented
- [ ] Template format followed

### Commit & File Management

**Commit Messages**
- Adding: `feat: add [agent-name] system prompt`
- Updating: `fix: update [agent-name] prompt from latest source`
- Documentation: `docs: improve [specific area]`

**File Management Rules**
- NEVER create files unless absolutely necessary
- Always prefer editing existing files over creating new ones
- Follow the established directory structure

### Testing & Validation

When working with this project:
1. Verify all URLs are accessible
2. Check that extracted prompts are complete
3. Ensure proper formatting and attribution
4. Validate against the quality checklist

### Important Notes

- This is a research library for understanding AI agent architectures
- Focus on defensive security analysis only
- All prompt extraction should be for legitimate research purposes
- Maintain high standards for source attribution and accuracy
