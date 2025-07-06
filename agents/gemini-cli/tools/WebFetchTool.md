# WebFetchTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/web-fetch.ts
**Location:** WebFetchTool class
**Retrieved:** 2025-01-06

---

## Description

Processes content from URL(s), including local and private network addresses (e.g., localhost), embedded in a prompt. Include up to 20 URLs and instructions directly in the 'prompt' parameter.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "prompt": {
      "type": "string",
      "description": "A comprehensive prompt that includes the URL(s) (up to 20) to fetch and specific instructions on how to process their content"
    }
  },
  "required": ["prompt"],
  "additionalProperties": false
}
```