# GrepTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/grep.ts
**Location:** GrepTool class
**Retrieved:** 2025-01-06

---

## Description

Searches for a regular expression pattern within the content of files in a specified directory (or current working directory).

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "pattern": {
      "type": "string",
      "description": "The regular expression (regex) pattern to search for within file contents"
    },
    "path": {
      "type": "string",
      "description": "Optional: The absolute path to the directory to search within"
    },
    "include": {
      "type": "string",
      "description": "Optional: A glob pattern to filter which files are searched"
    }
  },
  "required": ["pattern"],
  "additionalProperties": false
}
```