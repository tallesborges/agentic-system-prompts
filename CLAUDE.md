# Project: AI Agent System Prompts Library

## Contribution Philosophy

The guiding principles for this project are:

1. **Quality Over Quantity** - Better to have fewer, well-documented prompts than many incomplete ones
2. **Evidence-Based and Verifiable** - Every prompt must have clear source attribution and be verifiable
3. **Completeness** - Capture the full system prompt including all dynamic parts, examples, and conditional logic

## The Goal: Capturing the Complete System Prompt

A system prompt is rarely just a single block of text. Modern AI agents use sophisticated prompt engineering that includes:

- **Static Foundation** - The core, unchanging instructions
- **Dynamic Placeholders** - Variables for user input, context, or environment data
- **Conditional Logic** - Sections that appear based on certain conditions (git repos, sandbox mode, etc.)
- **Examples & Few-Shot Learning** - Hardcoded interaction examples
- **Tool Definitions** - Function schemas and capabilities
- **Context Injection** - File contents, project structure, user preferences

Our goal is to reconstruct and document the **complete prompt template** as it would be sent to the AI model.

## Contribution Workflow

### Step 1: Prompt Discovery & Extraction

System prompts can be found through various methods, listed from most to least reliable:

**Public Source Code** (Preferred)
- Analyze official open-source repositories on GitHub, GitLab, etc.
- Search for keywords: `prompt`, `system_message`, `instructions`, `getCoreSystemPrompt()`, `SYSTEM_PROMPT`
- Look in common files: `prompts.ts`, `prompts.py`, `main.py`, `cli.py`, `constants.py`

**Official Documentation**
- API documentation, technical blog posts, research papers
- Company engineering blogs often detail prompt engineering approaches

**Network Traffic Analysis**
- Inspect API requests from official applications (for research purposes)
- Look for instruction fields in request payloads
- Useful for closed-source tools with web interfaces

**Application Analysis**
- Mobile/desktop app reverse engineering
- Browser extension inspection
- Configuration file analysis

### Step 2: Prompt Analysis & Reconstruction

When analyzing discovered prompts, identify and document:

**Static Components**
- Core instructions that never change
- Agent personality and behavior guidelines
- Task-specific instructions

**Dynamic Components**
- Template variables (e.g., `${username}`, `{working_directory}`)
- Environment-specific sections (sandbox detection, git repository status)
- User preference injections

**Conditional Logic**
- Platform-specific instructions (macOS vs Linux vs Windows)
- Feature flags or capability toggles
- Context-dependent sections

**Examples and Patterns**
- Interaction examples showing expected input/output patterns
- Tool usage demonstrations
- Error handling examples

### Step 3: Formatting & Submission

**File Structure**
- Create: `agents/[agent-name]/system-prompt.md`
- Use lowercase, kebab-case naming (e.g., `claude-code`, `gemini-cli`)

**Content Template**
```markdown
# [Agent Name] System Prompt

**Source:** [Direct URL to source]
**Location:** [Specific function, file, or API endpoint]
**Retrieved:** [YYYY-MM-DD]

---

[Complete system prompt text with dynamic placeholders in their actual positions]
```

**Source Attribution Requirements**
- Include direct, accessible URLs
- Specify exact location (function name, line numbers if applicable)
- Note any dynamic substitution patterns
- Document extraction method used

## File Structure Convention

```
agents/
├── agent-name/
│   └── system-prompt.md
├── another-agent/
│   └── system-prompt.md
└── ...
```

## Quality Standards

**Completeness Verification**
- [ ] All conditional sections included
- [ ] Dynamic placeholders documented in context
- [ ] Examples and interaction patterns captured
- [ ] Tool definitions included (if applicable)

**Source Verification**
- [ ] Source URL is accessible
- [ ] Location information is specific and accurate
- [ ] Extraction method is documented
- [ ] Retrieved date is current

**Documentation Standards**
- [ ] Follows the standard template format
- [ ] Uses clear, descriptive agent names
- [ ] Includes all required metadata
- [ ] Preserves original formatting and structure

## Case Studies

For practical examples of these principles in action:

- **[Gemini CLI Analysis](./agents/gemini-cli/system-prompt.md)** - GitHub source code extraction
- **[Codex CLI Analysis](./agents/codex-cli/system-prompt.md)** - Combined GitHub + network traffic approach

## Tools & Commands

**Essential Tools for Discovery**
- `WebFetch` - Access raw files from URLs
- `Grep/Glob` - Search codebases for prompt patterns  
- `curl` - Direct file retrieval from repositories
- `rg` (ripgrep) - Fast searching with gitignore respect

**Common Search Patterns**
```bash
# GitHub raw file access
curl -s "https://raw.githubusercontent.com/[owner]/[repo]/[branch]/path/to/file"

# Search for prompt functions
grep -rn "prompt\|PROMPT\|system\|instructions" .
rg "getCoreSystemPrompt|getSystemPrompt|buildPrompt"
```

## Commit Conventions

- **Adding new agent:** `feat: add [agent-name] system prompt`
- **Updating existing:** `fix: update [agent-name] prompt from latest source`  
- **Documentation:** `docs: improve [specific area]`

## Review Process

Pull requests will be reviewed for:
1. **Completeness** - All dynamic parts and examples included
2. **Attribution** - Clear, accessible source documentation
3. **Accuracy** - Faithful reproduction of original prompt
4. **Format** - Adherence to template and naming conventions

Remember: This library's value comes from providing researchers, developers, and AI practitioners with accurate, complete documentation of how production AI agents actually work.