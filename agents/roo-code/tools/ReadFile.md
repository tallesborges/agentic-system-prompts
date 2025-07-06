# ReadFile Tool

**Source:** https://github.com/RooCodeInc/Roo-Code/tree/main/src/core/prompts/tools  
**Location:** src/core/prompts/tools/read-file.ts - getReadFileDescription function  
**Retrieved:** 2025-07-06

---

## Description

Request to read the contents of one or more files. The tool outputs line-numbered content (e.g. "1 | const x = 1") for easy reference when creating diffs or discussing code. Use line ranges to efficiently read specific portions of large files. Supports text extraction from PDF and DOCX files, but may not handle other binary files properly.

**IMPORTANT: You can read a maximum of 5 files in a single request.** If you need to read more files, use multiple sequential read_file requests.

By specifying line ranges, you can efficiently read specific portions of large files without loading the entire file into memory.

Parameters:
- args: Contains one or more file elements, where each file contains:
  - path: (required) File path (relative to workspace directory)
  - line_range: (optional) One or more line range elements in format "start-end" (1-based, inclusive)

Usage:
```xml
<read_file>
<args>
  <file>
    <path>path/to/file</path>
    <line_range>start-end</line_range>
  </file>
</args>
</read_file>
```

Examples:

1. Reading a single file:
```xml
<read_file>
<args>
  <file>
    <path>src/app.ts</path>
    <line_range>1-1000</line_range>
  </file>
</args>
</read_file>
```

2. Reading multiple files (within the 5-file limit):
```xml
<read_file>
<args>
  <file>
    <path>src/app.ts</path>
    <line_range>1-50</line_range>
    <line_range>100-150</line_range>
  </file>
  <file>
    <path>src/utils.ts</path>
    <line_range>10-20</line_range>
  </file>
</args>
</read_file>
```

3. Reading an entire file:
```xml
<read_file>
<args>
  <file>
    <path>config.json</path>
  </file>
</args>
</read_file>
```

IMPORTANT: You MUST use this Efficient Reading Strategy:
- You MUST read all related files and implementations together in a single operation (up to 5 files at once)
- You MUST obtain all necessary context before proceeding with changes
- You MUST use line ranges to read specific portions of large files, rather than reading entire files when not needed
- You MUST combine adjacent line ranges (<10 lines apart)
- You MUST use multiple ranges for content separated by >10 lines
- You MUST include sufficient line context for planned modifications while keeping ranges minimal
- When you need to read more than 5 files, prioritize the most critical files first, then use subsequent read_file requests for additional files