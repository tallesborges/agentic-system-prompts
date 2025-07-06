# ListDirectory Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/list_directory_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Lists files and directories in a given path. Prefer the `grep` or `find_path` tools when searching the codebase.

## Input Schema

```json
{
  "required": [
    "path"
  ],
  "properties": {
    "path": {
      "description": "The fully-qualified path of the directory to list in the project.\n\nThis path should never be absolute, and the first component of the path should always be a root directory in a project.\n\n<example>\nIf the project has the following root directories:\n\n- directory1\n- directory2\n\nYou can list the contents of `directory1` by using the path `directory1`.\n</example>\n\n<example>\nIf the project has the following root directories:\n\n- foo\n- bar\n\nIf you wanna list contents in the directory `foo/baz`, you should use the path `foo/baz`.\n</example>",
      "type": "string"
    }
  },
  "type": "object",
  "additionalProperties": false
}
```