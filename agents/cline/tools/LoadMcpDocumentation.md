# LoadMcpDocumentation Tool

**Source:** https://raw.githubusercontent.com/cline/cline/main/src/core/tools/loadMcpDocumentationTool.ts
**Location:** loadMcpDocumentationToolDefinition function
**Retrieved:** 2025-07-06

---

## Description

Load documentation about creating MCP servers. This tool should be used when the user requests to create or install an MCP server (the user may ask you something along the lines of "add a tool" that does some function, in other words to create an MCP server that provides tools and resources that may connect to external APIs for example. You have the ability to create an MCP server and add it to a configuration file that will then expose the tools and resources for you to use with `UseMCPTool` and `AccessMCPResource`). The documentation provides detailed information about the MCP server creation process, including setup instructions, best practices, and examples.

## Input Schema

```json
{
  "type": "object",
  "properties": {},
  "required": []
}
```