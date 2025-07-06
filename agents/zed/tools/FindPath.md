# FindPath Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/find_path_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Fast file path pattern matching tool that works with any codebase size

- Supports glob patterns like "**/*.js" or "src/**/*.ts"
- Returns matching file paths sorted alphabetically
- Prefer the `grep` tool to this tool when searching for symbols unless you have specific information about paths.
- Use this tool when you need to find files by name patterns
- Results are paginated with 50 matches per page. Use the optional 'offset' parameter to request subsequent pages.

## Input Schema

```json
{
  "required": [
    "glob"
  ],
  "properties": {
    "glob": {
      "description": "The glob to match against every path in the project.\n\n<example>\nIf the project has the following root directories:\n\n- directory1/a/something.txt\n- directory2/a/things.txt\n- directory3/a/other.txt\n\nYou can get back the first two paths by providing a glob of \"*thing*.txt\"\n</example>",
      "type": "string"
    },
    "offset": {
      "description": "Optional starting position for paginated results (0-based). When not provided, starts from the beginning.",
      "type": "integer",
      "format": "uint",
      "minimum": 0,
      "default": 0
    }
  },
  "type": "object",
  "additionalProperties": false
}
```