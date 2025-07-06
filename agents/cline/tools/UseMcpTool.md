# UseMcpTool Tool

**Source:** https://raw.githubusercontent.com/cline/cline/main/src/core/tools/useMcpTool.ts
**Location:** useMCPToolDefinition constant
**Retrieved:** 2025-07-06

---

## Description

Request to use a tool provided by a connected MCP server. Each MCP server can provide multiple tools with different capabilities. Tools have defined input schemas that specify required and optional parameters.

## Input Schema

```json
{
  "type": "object",
  "properties": {
    "server_name": {
      "type": "string",
      "description": "The name of the MCP server providing the tool"
    },
    "tool_name": {
      "type": "string",
      "description": "The name of the tool to execute"
    },
    "arguments": {
      "type": "object",
      "description": "A JSON object containing the tool's input parameters, following the tool's input schema"
    }
  },
  "required": ["server_name", "tool_name", "arguments"]
}
```