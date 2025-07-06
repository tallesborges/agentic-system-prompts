# WebSearchTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/web-search.ts
**Location:** WebSearchTool class
**Retrieved:** 2025-01-06

---

## Description

Performs a web search using Google Search (via the Gemini API) and returns the results. This tool is useful for finding information on the internet based on a query.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "query": {
      "type": "string",
      "description": "The search query to find information on the web."
    }
  },
  "required": ["query"],
  "additionalProperties": false
}
```