# SwitchMode Tool

**Source:** https://github.com/RooCodeInc/Roo-Code/tree/main/src/core/prompts/tools  
**Location:** src/core/prompts/tools/switch-mode.ts - getSwitchModeDescription function  
**Retrieved:** 2025-07-06

---

## Description

Request to switch to a different mode. This tool allows modes to request switching to another mode when needed, such as switching to Code mode to make code changes. The user must approve the mode switch.

Parameters:
- mode_slug: (required) The slug of the mode to switch to (e.g., "code", "ask", "architect")
- reason: (optional) The reason for switching modes

Usage:
```xml
<switch_mode>
<mode_slug>Mode slug here</mode_slug>
<reason>Reason for switching here</reason>
</switch_mode>
```

Example: Requesting to switch to code mode
```xml
<switch_mode>
<mode_slug>code</mode_slug>
<reason>Need to make code changes</reason>
</switch_mode>
```