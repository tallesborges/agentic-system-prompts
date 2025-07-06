# ListCodeDefinitionNames Tool

**Source:** https://raw.githubusercontent.com/cline/cline/main/src/core/tools/listCodeDefinitionNamesTool.ts
**Location:** listCodeDefinitionNamesToolDefinition function
**Retrieved:** 2025-07-06

---

## Description

Request to list definition names (classes, functions, methods, etc.) used in source code files at the top level of the specified directory. This tool provides insights into the codebase structure and important constructs, encapsulating high-level concepts and relationships that are crucial for understanding the overall architecture.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "path": {
      "type": "string",
      "description": "The path of the directory (relative to the current working directory) to list top level source code definitions for."
    }
  },
  "required": ["path"]
}
```