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
- Tool documentation: `agents/[agent-name]/tools/[ToolName].md`
- Use kebab-case naming (e.g., `claude-code`, `gemini-cli`)

**Standard Template Formats**

*System Prompt Format:*
```markdown
# [Agent Name] System Prompt

**Source:** [Direct URL to source]
**Location:** [Specific function/file/API endpoint]
**Retrieved:** [YYYY-MM-DD]

---

[Complete system prompt with dynamic placeholders]
```

*Tool Documentation Format:*
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
[Original JSON schema from API with proper formatting]
```
```

### Discovery & Extraction Methods

**Primary Sources (in order of reliability)**
1. **Public Source Code** - GitHub/GitLab repositories
2. **Official Documentation** - API docs, technical blogs
3. **Network Analysis** - API request inspection (research only)
4. **Application Analysis** - Reverse engineering, config files

**Key Search Patterns**
- **Prompts**: `prompt`, `system_message`, `instructions`, `getCoreSystemPrompt()`
- **Tools**: `tools`, `functions`, `input_schema`, `description`
- **Common files**: `prompts.ts`, `prompts.py`, `main.py`, `cli.py`, `constants.py`
- **API requests**: Look for complete request payloads with system prompts and tool definitions

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

*For System Prompts:*
- **Static Components** - Core instructions, personality guidelines
- **Dynamic Components** - Template variables, environment-specific sections
- **Conditional Logic** - Platform-specific instructions, feature toggles
- **Examples** - Interaction patterns, tool usage demonstrations

*For Tools:*
- **Complete Tool Definition** - Name, description, and full input schema
- **Original API Specifications** - Exact JSON schema from source
- **Usage Instructions** - All original documentation and examples
- **Parameter Details** - Required/optional fields, types, constraints

**Quality Checklist**

*System Prompts:*
- [ ] All conditional sections included
- [ ] Dynamic placeholders documented
- [ ] Source URL accessible and specific
- [ ] Extraction method documented
- [ ] Template format followed

*Tools:*
- [ ] Original tool description preserved exactly
- [ ] Complete JSON schema included
- [ ] All usage notes and examples captured
- [ ] Parameter requirements documented
- [ ] Source attribution complete

### Commit & File Management

**Commit Messages**
- Adding agent: `feat: add [agent-name] system prompt`
- Adding tools: `feat: add [agent-name] tool documentation`
- Updating: `fix: update [agent-name] prompt from latest source`
- Documentation: `docs: improve [specific area]`

**File Management Rules**
- NEVER create files unless absolutely necessary
- Always prefer editing existing files over creating new ones
- Follow the established directory structure
- Tools should be in `agents/[agent-name]/tools/` directory
- Use consistent naming: `[ToolName].md` (e.g., `MultiEdit.md`, `WebFetch.md`)

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

### Tool Documentation Best Practices

**Content Integrity**
- Preserve exact original descriptions from API sources
- Never modify, add to, or interpret tool descriptions
- Use original JSON schemas without transformation
- Only format for readability (indentation, line breaks)

**Format Consistency**
- Use markdown format with source metadata header
- Separate Description and Input Schema sections clearly
- Format JSON schemas with proper indentation for readability
- Maintain consistent tool naming conventions

**Source Attribution**
- Always include source, location, and retrieval date
- Specify exact API endpoint or request payload location
- Enable verification and future updates
