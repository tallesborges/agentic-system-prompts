# Thinking Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/thinking_tool.rs
**Retrieved:** 2025-07-06

---

## Description

A tool for thinking through problems, brainstorming ideas, or planning without executing any actions. Use this tool when you need to work through complex problems, develop strategies, or outline approaches before taking action.

## Input Schema

```json
{
  "required": [
    "content"
  ],
  "properties": {
    "content": {
      "description": "Content to think about. This should be a description of what to think about or a problem to solve.",
      "type": "string"
    }
  },
  "type": "object",
  "additionalProperties": false
}
```