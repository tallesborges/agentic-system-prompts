# ListFiles Tool

**Source:** https://github.com/RooCodeInc/Roo-Code/tree/main/src/core/prompts/tools  
**Location:** src/core/prompts/tools/list-files.ts - getListFilesDescription function  
**Retrieved:** 2025-07-06

---

## Description

Request to list files and directories within the specified directory. If recursive is true, it will list all files and directories recursively. If recursive is false or not provided, it will only list the top-level contents. Do not use this tool to confirm the existence of files you may have created, as the user will let you know if the files were created successfully or not.

Parameters:
- path: (required) The path of the directory to list contents for (relative to the current workspace directory)
- recursive: (optional) Whether to list files recursively. Use true for recursive listing, false or omit for top-level only.

Usage:
```xml
<list_files>
<path>Directory path here</path>
<recursive>true or false (optional)</recursive>
</list_files>
```

Example: Requesting to list all files in the current directory
```xml
<list_files>
<path>.</path>
<recursive>false</recursive>
</list_files>
```