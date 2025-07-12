# Claude Code Guidelines - Agentic System Prompts Repository

This document provides specific instructions for working on the `agentic-system-prompts` repository. Follow these guidelines to maintain consistency and quality across all agent documentation.

## Repository Purpose & Philosophy

This repository documents **production AI coding agents** for research and educational purposes. The focus is on:
- **Authenticity**: Preserve exact prompts and tool definitions as they exist in production
- **Research value**: Enable comparative analysis and pattern recognition
- **Legal clarity**: Proper attribution and minimal modification of source material
- **Developer accessibility**: Clean, readable formats that developers can understand and use

## File Format Standards

### System Prompts: Use Jinja2 (.j2)

**Primary format**: `.j2` (Jinja2 template)
- For dynamic prompts with variables and template logic
- No GitHub markdown rendering interference
- Self-documenting template structure
- Python ecosystem compatibility for analysis

**Structure**:
```jinja2
{#
  Agent: [Agent Name]
  Version: [Version]
  Extracted: [YYYY-MM-DD]
  Source: [GitHub URL to exact file with line numbers]
  Tokens: ~[Estimated token count]
  Tools: [comma-separated list]
#}

[Exact prompt content with Jinja2 variables]
```

### Tool Definitions: Use YAML (.yml)

**Primary format**: `.yml` (YAML)
- For multi-line text content and clean structure
- Raw tool definitions only (no additional documentation)
- Perfect for descriptions, examples, and safety instructions
- Easy to read and maintain

**Structure**:
```yaml
# Source: [GitHub URL to exact file with line numbers]
# Extracted: [YYYY-MM-DD]

name: [tool_name]
description: |
  [Multi-line description exactly as in source]

parameters:
  type: object
  properties:
    [exact parameter schema from source]
  required:
    - [required_fields]

# Include any additional fields present in original definition
safety_instructions: |
  [If present in original]

examples: |
  [If present in original]
```

## Directory Structure

Follow this exact structure for all agents:

```
agents/[agent-name]/
├── README.md                    # Agent overview, links, and summary
├── system-prompt.j2            # Jinja2 template format with variables
└── tools/                      # Tool definitions directory
    ├── [tool_name].yml        # YAML format for each tool
    ├── [tool_name_2].yml      # Additional tools
    └── ...
```

## Naming Conventions

### Repository and Directory Names
- Use kebab-case: `agentic-system-prompts`
- Agent directories: lowercase, match official name: `cline`, `aider`, `cursor`
- Tool files: match exact tool name from code: `edit_file.yml`, `run_command.yml`

### File Extensions
- System prompts: `.j2` (Jinja2 template format)
- Tool definitions: `.yml` (YAML format)
- Documentation: `.md`
- Examples: `.txt` for rendered output, `.md` for guides

## Content Guidelines

### System Prompt Extraction

1. **Find the exact source**: Locate the system prompt in the agent's codebase
2. **Copy verbatim**: Preserve exact text, spacing, and structure
3. **Identify variables**: Convert dynamic placeholders to Jinja2 syntax
4. **Add comprehensive metadata**: Include all required header information with precise source links
5. **Document conversion**: Note any format changes made during extraction

**Variable conversion examples**:
- `{user_input}` → `{{ user_input }}`
- `{file_contents}` → `{{ file_contents }}`
- Conditional logic: `{% if condition %}...{% endif %}`

### Tool Definition Extraction

1. **Locate tool schema**: Find JSON schema or function definition in code
2. **Extract definition only**: No additional documentation or examples beyond what exists in source
3. **Preserve structure**: Maintain exact parameter names, types, and descriptions
4. **Use YAML format**: Convert to clean YAML with multi-line support
5. **Add precise attribution**: Include source URL with line numbers

**What to include**:
- ✅ name, description, parameters (exactly as in source)
- ✅ required fields, defaults, types
- ✅ Original examples if present in source
- ✅ Safety instructions if present in source
- ❌ Additional documentation or analysis
- ❌ Usage statistics or patterns
- ❌ Community examples not from source

### Attribution Requirements

**Every file must include comprehensive source information**:
- **Source URL**: Direct link to exact file with line numbers (e.g., `#L15-45`)
- **Extraction date**: When the content was extracted (YYYY-MM-DD format)
- **Agent version**: If available from source repository
- **Conversion notes**: Any format changes made during extraction
- **Original licensing**: If different from repository default

**Example attribution for system prompt**:
```jinja2
{#
  Agent: Cline v2.1.0
  Extracted: 2024-01-15
  Source: https://github.com/cline/cline/blob/abc123456/src/core/prompts/system.ts#L15-45
  License: MIT
  Note: Converted from TypeScript template string to Jinja2 format
#}
```

**Example attribution for tool definition**:
```yaml
# Source: https://github.com/cline/cline/blob/abc123456/src/tools/edit_file.ts#L22-55
# Extracted: 2024-01-15
# License: MIT
# Note: Converted from JSON Schema object to YAML format
```

## Agent README Template

Each agent directory must include a README.md with this structure:

```markdown
# [Agent Name]

**Description**: [Brief description of what the agent does]
**Provider**: [Company/Organization]
**Repository**: [GitHub URL]
**Type**: [VS Code Extension/CLI Tool/Web Service/etc.]

## Overview

[1-2 paragraph description of the agent's capabilities and use case]

## System Prompt

- **Format**: Jinja2 template (`.j2`) with dynamic variables
- **Size**: ~[X] tokens
- **Variables**: [List key template variables]
- **Source**: [Direct link to original source]

## Tools

| Tool | Description | Parameters |
|------|-------------|------------|
| [tool_name] | [Brief description] | [Key parameters] |
| ... | ... | ... |

## Files Structure

- `system-prompt.j2` - Jinja2 template with variables and comprehensive attribution
- `tools/` - Individual tool definitions in YAML format with source links
- `examples/` - Usage examples and documentation
```

## Quality Standards

### Code Quality
- **Validate YAML**: Ensure all YAML files are valid and parseable
- **Check Jinja2**: Verify template syntax is correct
- **Test examples**: Ensure example values work with templates
- **Verify links**: All source URLs must be accessible and correct

### Research Standards
- **Accuracy**: Double-check all extracted content against source
- **Completeness**: Don't omit parts of the original definition
- **Consistency**: Follow format standards across all agents
- **Traceability**: Every piece of content must be traceable to its source

### Documentation Standards
- **Clear attribution**: Every file shows where content came from
- **Readable structure**: Consistent formatting and organization
- **Helpful examples**: Show how dynamic parts work in practice
- **Up-to-date info**: Regular checks against original sources

## Common Tasks

### Adding a New Agent

1. Create directory: `agents/[agent-name]/`
2. Extract system prompt → convert to `system-prompt.j2` with comprehensive attribution
3. Extract each tool → convert to `tools/[tool-name].yml` with source links
4. Create `README.md` using template above
5. Add examples showing template usage and variable substitution
6. Update main repository README with new agent

### Converting Existing Content

1. **Review current format**: Identify what needs conversion
2. **Find original sources**: Locate exact source files
3. **Apply new format**: Convert to .j2/.yml with enhanced attribution
4. **Document conversions**: Note any format changes in file headers
5. **Update documentation**: Ensure README reflects new structure and sourcing

### Updating Agent Information

1. **Check source repository**: Look for version updates and changes
2. **Compare changes**: Identify what has changed since last extraction
3. **Update extracted content**: Convert new versions with updated attribution
4. **Update metadata**: Version numbers, dates, etc.
5. **Document changes**: Note what was updated and when

## Repository Maintenance

### Regular Tasks
- Check source repositories for updates
- Validate all source links are still working
- Ensure YAML/Jinja2 files are valid and properly formatted
- Update extraction dates when content changes
- Monitor for new tools or prompt changes in tracked repositories

### Quality Checks
- Run YAML linting on all `.yml` files
- Test Jinja2 templates with sample data to ensure syntax is correct
- Verify all source URLs with line numbers are accessible
- Check for consistency in naming and structure across agents
- Ensure all required attribution metadata is present and accurate
- Validate that source links point to the exact extracted content

## Tools and Automation

### Recommended Tools
- **YAML validation**: `yamllint` for syntax checking
- **Jinja2 testing**: Python with Jinja2 library for template validation
- **Link checking**: Tools to verify source URLs are accessible
- **Format conversion**: Scripts to help convert between formats

### Automation Opportunities
- Script to extract tool definitions from source repositories
- Template validation in CI/CD pipeline
- Automated link checking
- Format consistency verification

### Tool Usage for This Project

**Common Commands**
```bash
# Search for prompt functions
rg "getCoreSystemPrompt|getSystemPrompt|buildPrompt"
```

### File Management

**When updating files:**
- Adding agent: Create new agent directory with proper structure
- Adding tools: Add tool definitions in YAML format
- Updating: Ensure source URLs are accurate
- Documentation: Keep README files comprehensive

---

**Remember**: This repository serves the research and educational community by making production AI agent prompts accessible and analyzable. Maintain high standards for accuracy, comprehensive attribution, and accessibility. The goal is to transform raw source material into clean, usable formats while preserving complete traceability to original sources. When in doubt, prioritize authenticity and detailed source documentation over convenience.
