# WriteFileTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/write-file.ts
**Location:** WriteFileTool class
**Retrieved:** 2025-01-06

---

## Description

Writes content to a specified file in the local filesystem. The user has the ability to modify `content`.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "file_path": {
      "type": "string",
      "description": "The absolute path to the file to write to (e.g., '/home/user/project/file.txt'). Relative paths are not supported."
    },
    "content": {
      "type": "string",
      "description": "The content to write to the file."
    },
    "modified_by_user": {
      "type": "boolean",
      "description": "Indicates whether the proposed content was modified by the user"
    }
  },
  "required": ["file_path", "content"],
  "additionalProperties": false
}
```