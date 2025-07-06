# DeletePath Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/delete_path_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Deletes the file or directory (and the directory's contents, recursively) at the specified path in the project, and returns confirmation of the deletion.

## Input Schema

```json
{
  "required": [
    "path"
  ],
  "properties": {
    "path": {
      "description": "The path of the file or directory to delete.\n\n<example>\nIf the project has the following files:\n\n- directory1/a/something.txt\n- directory2/a/things.txt\n- directory3/a/other.txt\n\nYou can delete the first file by providing a path of \"directory1/a/something.txt\"\n</example>",
      "type": "string"
    }
  },
  "type": "object",
  "additionalProperties": false
}
```