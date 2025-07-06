# LSTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/ls.ts
**Location:** LSTool class
**Retrieved:** 2025-01-06

---

## Description

Lists the names of files and subdirectories directly within a specified directory path. Can optionally ignore entries matching provided glob patterns.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "path": {
      "type": "string",
      "description": "The absolute path to the directory to list (must be absolute, not relative)"
    },
    "ignore": {
      "type": "array",
      "items": {
        "type": "string"
      },
      "description": "List of glob patterns to ignore"
    },
    "respect_git_ignore": {
      "type": "boolean",
      "description": "Whether to respect .gitignore patterns when listing files. Only available in git repositories.",
      "default": true
    }
  },
  "required": ["path"],
  "additionalProperties": false
}
```