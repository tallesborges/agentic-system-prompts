# ReadManyFilesTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/read-many-files.ts
**Location:** ReadManyFilesTool class
**Retrieved:** 2025-01-06

---

## Description

Reads content from multiple files specified by paths or glob patterns within a configured target directory. For text files, it concatenates their content into a single string.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "paths": {
      "type": "array",
      "items": {
        "type": "string"
      },
      "description": "Array of file/directory paths or glob patterns"
    },
    "include": {
      "type": "array",
      "items": {
        "type": "string"
      },
      "description": "Optional additional glob patterns to include files"
    },
    "exclude": {
      "type": "array",
      "items": {
        "type": "string"
      },
      "description": "Optional glob patterns to exclude files"
    },
    "recursive": {
      "type": "boolean",
      "description": "Optional boolean for recursive search",
      "default": true
    },
    "useDefaultExcludes": {
      "type": "boolean",
      "description": "Optional boolean to apply default exclusion patterns",
      "default": true
    },
    "respect_git_ignore": {
      "type": "boolean",
      "description": "Optional boolean to respect .gitignore patterns",
      "default": true
    }
  },
  "required": ["paths"],
  "additionalProperties": false
}
```