# MemoryTool

**Source:** https://raw.githubusercontent.com/google-gemini/gemini-cli/main/packages/core/src/tools/memoryTool.ts
**Location:** MemoryTool class
**Retrieved:** 2025-01-06

---

## Description

Saves a specific piece of information or fact to your long-term memory. Use this when the user explicitly asks you to remember something.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "fact": {
      "type": "string",
      "description": "The specific fact or piece of information to remember. Should be a clear, self-contained statement."
    }
  },
  "required": ["fact"],
  "additionalProperties": false
}
```