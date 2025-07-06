# Now Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/now_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Returns the current datetime in RFC 3339 format. Only use this tool when the user specifically asks for it or the current task would benefit from knowing the current datetime.

## Input Schema

```json
{
  "definitions": {
    "Timezone": {
      "oneOf": [
        {
          "description": "Use UTC for the datetime.",
          "type": "string",
          "const": "utc"
        },
        {
          "description": "Use local time for the datetime.",
          "type": "string",
          "const": "local"
        }
      ]
    }
  },
  "required": [
    "timezone"
  ],
  "type": "object",
  "properties": {
    "timezone": {
      "description": "The timezone to use for the datetime.",
      "allOf": [
        {
          "$ref": "#/definitions/Timezone"
        }
      ]
    }
  },
  "additionalProperties": false
}
```