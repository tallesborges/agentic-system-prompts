# LS Tool

**Source:** https://raw.githubusercontent.com/cline/cline/main/src/core/tools/lsTool.ts
**Location:** lsToolDefinition constant
**Retrieved:** 2025-07-06

---

## Description

Lists files and directories in a given path. The path parameter must be an absolute path, not a relative path. You should generally prefer the Glob and Grep tools, if you know which directories to search.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "path": {
      "type": "string",
      "description": "The path of the directory to list contents for"
    }
  },
  "required": ["path"]
}
```