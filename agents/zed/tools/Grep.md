# Grep Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/grep_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Searches the contents of files in the project with a regular expression

- Prefer this tool to path search when searching for symbols in the project, because you won't need to guess what path it's in.
- Supports full regex syntax (eg. "log.*Error", "function\\s+\\w+", etc.)
- Pass an `include_pattern` if you know how to narrow your search on the files system
- Never use this tool to search for paths. Only search file contents with this tool.
- Use this tool when you need to find files containing specific patterns
- Results are paginated with 20 matches per page. Use the optional 'offset' parameter to request subsequent pages.
- DO NOT use HTML entities solely to escape characters in the tool parameters.

## Input Schema

```json
{
  "required": [
    "regex"
  ],
  "properties": {
    "regex": {
      "description": "A regex pattern to search for in the entire project. Note that the regex will be parsed by the Rust `regex` crate.\n\nDo NOT specify a path here! This will only be matched against the code **content**.",
      "type": "string"
    },
    "include_pattern": {
      "description": "A glob pattern for the paths of files to include in the search. Supports standard glob patterns like \"**/*.rs\" or \"src/**/*.ts\". If omitted, all files in the project will be searched.",
      "type": [
        "string",
        "null"
      ]
    },
    "offset": {
      "description": "Optional starting position for paginated results (0-based). When not provided, starts from the beginning.",
      "type": "integer",
      "format": "uint32",
      "minimum": 0,
      "default": 0
    },
    "case_sensitive": {
      "description": "Whether the regex is case-sensitive. Defaults to false (case-insensitive).",
      "type": "boolean",
      "default": false
    }
  },
  "type": "object",
  "additionalProperties": false
}
```