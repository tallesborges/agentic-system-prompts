# CopyPath Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/copy_path_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Copies a file or directory in the project, and returns confirmation that the copy succeeded.
Directory contents will be copied recursively (like `cp -r`).

This tool should be used when it's desirable to create a copy of a file or directory without modifying the original.
It's much more efficient than doing this by separately reading and then writing the file or directory's contents,
so this tool should be preferred over that approach whenever copying is the goal.

## Input Schema

```json
{
  "required": [
    "source_path",
    "destination_path"
  ],
  "properties": {
    "source_path": {
      "description": "The source path of the file or directory to copy. If a directory is specified, its contents will be copied recursively (like `cp -r`).\n\n<example>\nIf the project has the following files:\n\n- directory1/a/something.txt\n- directory2/a/things.txt\n- directory3/a/other.txt\n\nYou can copy the first file by providing a source_path of \"directory1/a/something.txt\"\n</example>",
      "type": "string"
    },
    "destination_path": {
      "description": "The destination path where the file or directory should be copied to.\n\n<example>\nTo copy \"directory1/a/something.txt\" to \"directory2/b/copy.txt\", provide a destination_path of \"directory2/b/copy.txt\"\n</example>",
      "type": "string"
    }
  },
  "type": "object",
  "additionalProperties": false
}
```