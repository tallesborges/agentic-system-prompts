# Read Tool

**Source:** https://raw.githubusercontent.com/cline/cline/main/src/core/tools/readTool.ts
**Location:** readToolDefinition function
**Retrieved:** 2025-07-06

---

## Description

Request to read the contents of a file at the specified path. Use this when you need to examine the contents of an existing file you do not know the contents of, for example to analyze code, review text files, or extract information from configuration files. Automatically extracts raw text from PDF and DOCX files. May not be suitable for other types of binary files, as it returns the raw content as a string.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "file_path": {
      "type": "string",
      "description": "The path of the file to read (relative to the current working directory)"
    }
  },
  "required": ["file_path"]
}
```