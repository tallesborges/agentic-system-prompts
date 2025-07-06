# GlobTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/glob.ts
**Location:** GlobTool class
**Retrieved:** 2025-01-06

---

## Description

Efficiently finds files matching specific glob patterns (e.g., `src/**/*.ts`, `**/*.md`), returning absolute paths sorted by modification time.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "pattern": {
      "type": "string",
      "description": "Glob pattern to match files (e.g., '**/*.py', 'docs/*.md')"
    },
    "path": {
      "type": "string",
      "description": "Absolute path to search directory"
    },
    "case_sensitive": {
      "type": "boolean",
      "description": "Whether search is case-sensitive",
      "default": false
    },
    "respect_git_ignore": {
      "type": "boolean",
      "description": "Respect .gitignore patterns",
      "default": true
    }
  },
  "required": ["pattern"],
  "additionalProperties": false
}
```