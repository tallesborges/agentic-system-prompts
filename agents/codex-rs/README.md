# Codex Cli

**Description**: Rust-implemented command-line coding assistant with patch-based file editing
**Provider**: OpenAI
**Repository**: https://github.com/openai/codex
**Type**: CLI Tool

## Overview

// TODO

## System Prompt

- **Format**: Jinja2 template (`.j2`) with dynamic variables
- **Size**: ~1,500 tokens
- **Variables**: `current_file`, `file_contents`, `user_request`
- **Source**: https://raw.githubusercontent.com/openai/codex/8d35ad0ef79a0df564d2edc3b5e5624c53c7bde7/codex-rs/core/prompt.md

## Tools

| Tool | Description | Parameters | Used For |
|------|-------------|------------|----------|
| local_shell | Shell execution (implementation details in prompt) | None (empty enum variant) | Codex models |
| shell | Runs a shell command, and returns its output | command (array of strings), workdir (string), timeout (number) | Other models |

## Source Information

- **Repository**: https://github.com/openai/codex
- **Version**: Not specified in source
- **Commit**: 8d35ad0ef79a0df564d2edc3b5e5624c53c7bde7
- **Extracted**: 2025-01-12
- **Last Updated**: 2025-01-12

## Files Structure

- `system-prompt.j2` - Jinja2 template with variables and comprehensive attribution
- `tools/` - Individual tool definitions in YAML format with source links
  - `local_shell.yml` - Shell execution for codex models (empty enum variant)
  - `shell.yml` - Shell command execution tool for other models
