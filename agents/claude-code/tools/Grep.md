# Grep Tool

**Source:** Anthropic Claude Code API Request
**Location:** tools array in request payload
**Retrieved:** 2025-07-06

---

## Description

- Fast content search tool that works with any codebase size
- Searches file contents using regular expressions
- Supports full regex syntax (eg. "log.*Error", "function\\s+\\w+", etc.)
- Filter files by pattern with the include parameter (eg. "*.js", "*.{ts,tsx}")
- Returns file paths with at least one match sorted by modification time
- Use this tool when you need to find files containing specific patterns
- If you need to identify/count the number of matches within files, use the Bash tool with `rg` (ripgrep) directly. Do NOT use `grep`.
- When you are doing an open ended search that may require multiple rounds of globbing and grepping, use the Agent tool instead

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "pattern": {
      "type": "string",
      "description": "The regular expression pattern to search for in file contents"
    },
    "path": {
      "type": "string",
      "description": "The directory to search in. Defaults to the current working directory."
    },
    "include": {
      "type": "string",
      "description": "File pattern to include in the search (e.g. \"*.js\", \"*.{ts,tsx}\")"
    }
  },
  "required": [
    "pattern"
  ],
  "additionalProperties": false,
  "$schema": "http://json-schema.org/draft-07/schema#"
}
```