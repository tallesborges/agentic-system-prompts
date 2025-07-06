# Fetch Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/fetch_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Fetches a URL and returns the content as Markdown.

## Input Schema

```json
{
  "required": [
    "url"
  ],
  "properties": {
    "url": {
      "description": "The URL to fetch.",
      "type": "string"
    }
  },
  "type": "object",
  "additionalProperties": false
}
```