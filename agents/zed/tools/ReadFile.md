# ReadFile Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/read_file_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Reads the content of the given file in the project.

- Never attempt to read a path that hasn't been previously mentioned.

## Input Schema

```json
{
  "required": [
    "path"
  ],
  "properties": {
    "path": {
      "description": "The relative path of the file to read.\n\nThis path should never be absolute, and the first component of the path should always be a root directory in a project.\n\n<example>\nIf the project has the following root directories:\n\n- /a/b/directory1\n- /c/d/directory2\n\nIf you want to access `file.txt` in `directory1`, you should use the path `directory1/file.txt`.\nIf you want to access `file.txt` in `directory2`, you should use the path `directory2/file.txt`.\n</example>",
      "type": "string"
    },
    "start_line": {
      "description": "Optional line number to start reading on (1-based index)",
      "type": [
        "integer",
        "null"
      ],
      "format": "uint32",
      "minimum": 0,
      "default": null
    },
    "end_line": {
      "description": "Optional line number to end reading on (1-based index, inclusive)",
      "type": [
        "integer",
        "null"
      ],
      "format": "uint32",
      "minimum": 0,
      "default": null
    }
  },
  "description": "If the model requests to read a file whose size exceeds this, then",
  "type": "object",
  "additionalProperties": false
}
```