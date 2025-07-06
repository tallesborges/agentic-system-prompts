# CreateDirectory Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/create_directory_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Creates a new directory at the specified path within the project. Returns confirmation that the directory was created.

This tool creates a directory and all necessary parent directories (similar to `mkdir -p`). It should be used whenever you need to create new directories within the project.

## Input Schema

```json
{
  "required": [
    "path"
  ],
  "properties": {
    "path": {
      "description": "The path of the new directory.\n\n<example>\nIf the project has the following structure:\n\n- directory1/\n- directory2/\n\nYou can create a new directory by providing a path of \"directory1/new_directory\"\n</example>",
      "type": "string"
    }
  },
  "type": "object",
  "additionalProperties": false
}
```