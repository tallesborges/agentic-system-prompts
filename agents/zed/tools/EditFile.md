# EditFile Tool

**Source:** https://github.com/zed-industries/zed
**Location:** crates/assistant_tools/src/edit_file_tool.rs
**Retrieved:** 2025-07-06

---

## Description

This is a tool for creating a new file or editing an existing file. For moving or renaming files, you should generally use the `terminal` tool with the 'mv' command instead.

Before using this tool:

1. Use the `read_file` tool to understand the file's contents and context

2. Verify the directory path is correct (only applicable when creating new files):
   - Use the `list_directory` tool to verify the parent directory exists and is the correct location

## Input Schema

```json
{
  "definitions": {
    "EditFileMode": {
      "type": "string",
      "enum": [
        "edit",
        "create",
        "overwrite"
      ]
    }
  },
  "required": [
    "display_description",
    "path",
    "mode"
  ],
  "type": "object",
  "properties": {
    "display_description": {
      "description": "A one-line, user-friendly markdown description of the edit. This will be shown in the UI and also passed to another model to perform the edit.\n\nBe terse, but also descriptive in what you want to achieve with this edit. Avoid generic instructions.\n\nNEVER mention the file path in this description.\n\n<example>Fix API endpoint URLs</example>\n<example>Update copyright year in `page_footer`</example>\n\nMake sure to include this field before all the others in the input object so that we can display it immediately.",
      "type": "string"
    },
    "path": {
      "description": "The full path of the file to create or modify in the project.\n\nWARNING: When specifying which file path need changing, you MUST start each path with one of the project's root directories.\n\nThe following examples assume we have two root directories in the project:\n- /a/b/backend\n- /c/d/frontend\n\n<example>\n`backend/src/main.rs`\n\nNotice how the file path starts with `backend`. Without that, the path would be ambiguous and the call would fail!\n</example>\n\n<example>\n`frontend/db.js`\n</example>",
      "type": "string"
    },
    "mode": {
      "description": "The mode of operation on the file. Possible values:\n- 'edit': Make granular edits to an existing file.\n- 'create': Create a new file if it doesn't exist.\n- 'overwrite': Replace the entire contents of an existing file.\n\nWhen a file already exists or you just created it, prefer editing it as opposed to recreating it from scratch.",
      "allOf": [
        {
          "$ref": "#/definitions/EditFileMode"
        }
      ]
    }
  },
  "additionalProperties": false
}
```