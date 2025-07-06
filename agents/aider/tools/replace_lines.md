# replace_lines Tool

**Source:** https://github.com/Aider-AI/aider/blob/main/aider/coders/editblock_func_coder.py
**Location:** `EditBlockFunctionCoder.functions[0]`
**Retrieved:** 2025-01-06

---

## Description

create or update one or more files

## Input Schema

```json
{
  "name": "replace_lines",
  "description": "create or update one or more files",
  "parameters": {
    "type": "object",
    "required": ["explanation", "edits"],
    "properties": {
      "explanation": {
        "type": "string",
        "description": "Step by step plan for the changes to be made to the code (future tense, markdown format)"
      },
      "edits": {
        "type": "array",
        "items": {
          "type": "object",
          "required": ["path", "original_lines", "updated_lines"],
          "properties": {
            "path": {
              "type": "string",
              "description": "Path of file to edit"
            },
            "original_lines": {
              "type": "array",
              "items": {
                "type": "string"
              },
              "description": "A unique stretch of lines from the original file, including all whitespace, without skipping any lines"
            },
            "updated_lines": {
              "type": "array",
              "items": {
                "type": "string"
              },
              "description": "New content to replace the `original_lines` with"
            }
          }
        }
      }
    }
  }
}
```

## Usage Notes

- This function is part of the **deprecated** `EditBlockFunctionCoder` class that was designed for function calling mode
- The current implementation throws a `RuntimeError` stating "Deprecated, needs to be refactored to support get_edits/apply_edits"
- Aider primarily uses the SEARCH/REPLACE block format in prompts rather than function calling for code edits
- The tool was designed to support both array-based and string-based formats for `original_lines` and `updated_lines`
- When used, it would validate that the function name is exactly "replace_lines"
- The implementation includes automatic newline handling and content validation