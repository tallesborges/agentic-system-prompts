# Diagnostics Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/diagnostics_tool.rs
**Retrieved:** 2025-07-06

---

## Description

Get errors and warnings for the project or a specific file.

This tool can be invoked after a series of edits to determine if further edits are necessary, or if the user asks to fix errors or warnings in their codebase.

When a path is provided, shows all diagnostics for that specific file.
When no path is provided, shows a summary of error and warning counts for all files in the project.

<example>
To get diagnostics for a specific file:
{
    "path": "src/main.rs"
}

To get a project-wide diagnostic summary:
{}
</example>

<guidelines>
- If you think you can fix a diagnostic, make 1-2 attempts and then give up.
- Don't remove code you've generated just because you can't fix an error. The user can help you fix it.
</guidelines>

## Input Schema

```json
{
  "properties": {
    "path": {
      "description": "The path to get diagnostics for. If not provided, returns a project-wide summary.\n\nThis path should never be absolute, and the first component of the path should always be a root directory in a project.\n\n<example>\nIf the project has the following root directories:\n\n- lorem\n- ipsum\n\nIf you wanna access diagnostics for `dolor.txt` in `ipsum`, you should use the path `ipsum/dolor.txt`.\n</example>",
      "type": [
        "string",
        "null"
      ]
    }
  },
  "type": "object",
  "additionalProperties": false
}
```