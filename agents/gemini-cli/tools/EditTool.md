# EditTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/edit.ts
**Location:** EditTool class
**Retrieved:** 2025-01-06

---

## Description

Replaces text within a file, with precise requirements for targeting text replacements. Can replace single or multiple occurrences of text.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "file_path": {
      "type": "string",
      "description": "The absolute path to the file to edit (e.g., '/home/user/project/file.txt'). Relative paths are not supported.",
      "pattern": "^/"
    },
    "old_string": {
      "type": "string",
      "description": "The exact literal text to replace. Must uniquely identify the text to change and include 3 lines of context before and after target text."
    },
    "new_string": {
      "type": "string",
      "description": "The exact literal text to replace `old_string` with. Match whitespace and indentation precisely."
    },
    "expected_replacements": {
      "type": "number",
      "description": "Optional number of replacements expected (defaults to 1)."
    }
  },
  "required": ["file_path", "old_string", "new_string"],
  "additionalProperties": false
}
```