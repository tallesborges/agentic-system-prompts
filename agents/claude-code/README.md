# Claude Code

**Description**: Anthropic's official CLI tool for Claude
**Provider**: Anthropic
**Repository**: https://github.com/anthropics/claude-code
**Type**: CLI Tool

## Overview

Claude Code is Anthropic's official command-line interface for Claude, designed to help users with software engineering tasks. It provides an interactive CLI environment with sophisticated tools for code manipulation, file management, search operations, and task planning. The agent emphasizes concise, direct communication and follows strict conventions for code quality and security.

The CLI is powered by Claude Opus 4 and features comprehensive tooling for development workflows, including support for Jupyter notebooks, web operations, and advanced task management capabilities.

## System Prompt

- **Format**: Jinja2 template (`.j2`) with dynamic variables
- **Size**: ~3500 tokens
- **Variables**: `allowed_tools`, `working_directory`, `is_git_repo`, `platform`, `os_version`, `today_date`, `current_branch`, `main_branch`, `git_status`, `recent_commits`
- **Source**: Production system prompt from Claude Code CLI

## Tools

| Tool | Description | Parameters |
|------|-------------|------------|
| Task | Launch autonomous agents for complex multi-step tasks | description, prompt, subagent_type |
| Bash | Execute bash commands with timeout and proper handling | command, timeout, description |
| Glob | Fast file pattern matching across codebases | pattern, path |
| Grep | Powerful ripgrep-based search with regex support | pattern, path, output_mode, various filters |
| LS | List files and directories with absolute paths | path, ignore |
| ExitPlanMode | Exit planning mode when ready to code | plan |
| Read | Read files including images, PDFs, and text | file_path, offset, limit |
| Edit | Perform exact string replacements in files | file_path, old_string, new_string, replace_all |
| MultiEdit | Multiple edits to a single file in one operation | file_path, edits array |
| Write | Write files to the filesystem | file_path, content |
| NotebookRead | Read Jupyter notebook cells and outputs | notebook_path, cell_id |
| NotebookEdit | Edit, insert, or delete Jupyter notebook cells | notebook_path, cell_id, new_source, cell_type, edit_mode |
| WebFetch | Fetch and process web content with AI | url, prompt |
| TodoWrite | Create and manage structured task lists | todos array |
| WebSearch | Search the web for current information | query, allowed_domains, blocked_domains |

## Files Structure

- `system-prompt.j2` - Jinja2 template with variables and comprehensive attribution
- `tools/` - Individual tool definitions in markdown format with YAML headers
  - `Task.md` - Task tool for launching autonomous agents
  - `Bash.md` - Bash command execution tool
  - `glob.md` - File pattern matching tool
  - `grep.md` - Ripgrep-based search tool
  - `ls.md` - Directory listing tool
  - `exit-plan-mode.md` - Plan mode exit tool
  - `Read.md` - File reading tool
  - `Edit.md` - File editing tool
  - `MultiEdit.md` - Multiple file edits tool
  - `Write.md` - File writing tool
  - `NotebookRead.md` - Jupyter notebook reading tool
  - `NotebookEdit.md` - Jupyter notebook editing tool
  - `WebFetch.md` - Web content fetching tool
  - `TodoWrite.md` - Task management tool
  - `WebSearch.md` - Web search tool