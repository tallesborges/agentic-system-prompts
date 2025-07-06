# WebFetch Tool

**Source:** https://raw.githubusercontent.com/cline/cline/main/src/core/tools/webFetchTool.ts
**Location:** webFetchToolDefinition constant
**Retrieved:** 2025-07-06

---

## Description

- Fetches content from a specified URL and processes into markdown
- Takes a URL as input
- Fetches the URL content, converts HTML to markdown
- Use this tool when you need to retrieve and analyze web content

Usage notes:
  - IMPORTANT: If an MCP-provided web fetch tool is available, prefer using that tool instead of this one, as it may have fewer restrictions.
  - The URL must be a fully-formed valid URL
  - HTTP URLs will be automatically upgraded to HTTPS
  - This tool is read-only and does not modify any files

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "url": {
      "type": "string",
      "format": "url",
      "description": "The URL to fetch content from"
    }
  },
  "required": ["url"]
}
```