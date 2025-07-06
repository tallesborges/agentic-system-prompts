# NewTask Tool

**Source:** https://github.com/RooCodeInc/Roo-Code/tree/main/src/core/prompts/tools  
**Location:** src/core/prompts/tools/new-task.ts - getNewTaskDescription function  
**Retrieved:** 2025-07-06

---

## Description

This will let you create a new task instance in the chosen mode using your provided message.

Parameters:
- mode: (required) The slug of the mode to start the new task in (e.g., "code", "debug", "architect").
- message: (required) The initial user message or instructions for this new task.

Usage:
```xml
<new_task>
<mode>your-mode-slug-here</mode>
<message>Your initial instructions here</message>
</new_task>
```

Example:
```xml
<new_task>
<mode>code</mode>
<message>Implement a new feature for the application.</message>
</new_task>
```