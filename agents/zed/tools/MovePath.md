# MovePath Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/move_path_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Moves or rename a file or directory in the project, and returns confirmation that the move succeeded.
If the source and destination directories are the same, but the filename is different, this performs
a rename. Otherwise, it performs a move.

This tool should be used when it's desirable to move or rename a file or directory without changing its contents at all.

## Input Schema

```json
{
  "required": [
    "source_path",
    "destination_path"
  ],
  "properties": {
    "source_path": {
      "description": "The source path of the file or directory to move/rename.\n\n<example>\nIf the project has the following files:\n\n- directory1/a/something.txt\n- directory2/a/things.txt\n- directory3/a/other.txt\n\nYou can move the first file by providing a source_path of \"directory1/a/something.txt\"\n</example>",
      "type": "string"
    },
    "destination_path": {
      "description": "The destination path where the file or directory should be moved/renamed to. If the paths are the same except for the filename, then this will be a rename.\n\n<example>\nTo move \"directory1/a/something.txt\" to \"directory2/b/renamed.txt\", provide a destination_path of \"directory2/b/renamed.txt\"\n</example>",
      "type": "string"
    }
  },
  "type": "object",
  "additionalProperties": false
}
```