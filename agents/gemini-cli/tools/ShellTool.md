# ShellTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/shell.ts
**Location:** ShellTool class
**Retrieved:** 2025-01-06

---

## Description

This tool executes a given shell command as `bash -c <command>`. Command can start background processes using `&`.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "command": {
      "type": "string",
      "description": "Exact bash command to execute"
    },
    "description": {
      "type": "string",
      "description": "Brief description of the command"
    },
    "directory": {
      "type": "string",
      "description": "Directory to run the command in, relative to project root"
    }
  },
  "required": ["command"],
  "additionalProperties": false
}
```