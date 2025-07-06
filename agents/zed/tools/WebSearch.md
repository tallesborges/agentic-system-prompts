# WebSearch Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/web_search_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Allows Claude to search the web and use the results to inform responses
- Provides up-to-date information for current events and recent data
- Returns search result information formatted as search result blocks
- Use this tool for accessing information beyond Claude's knowledge cutoff
- Searches are performed automatically within a single API call

Usage notes:
- Domain filtering is supported to include or block specific websites
- Web search is only available in the US
- Account for "Today's date" in <env>. For example, if <env> says "Today's date: 2025-07-01", and the user wants the latest docs, do not use 2024 in the search query. Use 2025.

## Input Schema

```json
{
  "required": [
    "query"
  ],
  "properties": {
    "query": {
      "description": "The search query to use",
      "minLength": 2,
      "type": "string"
    },
    "allowed_domains": {
      "description": "Only include search results from these domains",
      "items": {
        "type": "string"
      },
      "type": "array"
    },
    "blocked_domains": {
      "description": "Never include search results from these domains",
      "items": {
        "type": "string"
      },
      "type": "array"
    }
  },
  "type": "object",
  "additionalProperties": false
}
```