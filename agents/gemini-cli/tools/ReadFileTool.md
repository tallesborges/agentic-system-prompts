# ReadFileTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/read-file.ts
**Location:** ReadFileTool class
**Retrieved:** 2025-01-06

---

## Description

Reads and returns the content of a specified file from the local filesystem. Handles text, images (PNG, JPG, GIF, WEBP, SVG, BMP), and PDF files.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "absolute_path": {
      "type": "string",
      "description": "The absolute path to the file to read (e.g., '/home/user/project/file.txt'). Relative paths are not supported.",
      "pattern": "^/"
    },
    "offset": {
      "type": "number",
      "description": "For text files, the 0-based line number to start reading from. Requires 'limit' to be set."
    },
    "limit": {
      "type": "number",
      "description": "For text files, maximum number of lines to read. Use with 'offset' to paginate through large files."
    }
  },
  "required": ["absolute_path"],
  "additionalProperties": false
}
```