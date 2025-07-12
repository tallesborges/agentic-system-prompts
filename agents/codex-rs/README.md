# Codex Cli

**Description**: Rust-implemented command-line coding assistant with patch-based file editing\
**Provider**: OpenAI\
**Repository**: https://github.com/openai/codex \
**Type**: CLI Tool

## Overview

// TODO

## Files Structure

- [system-prompt.j2](system-prompt.j2) - Jinja2 template with variables and comprehensive attribution
- [tools/](tools/) - Individual tool definitions in YAML format with source links
  - [local_shell.yml](tools/local_shell.yml) - Shell execution for codex models (empty enum variant)
  - [shell.yml](tools/shell.yml) - Shell command execution tool for other models

## Tools

| Tool | Description | Parameters | Used For |
|------|-------------|------------|----------|
| local_shell | Shell execution | None (empty enum variant) | Codex models |
| shell | Runs a shell command, and returns its output | command (array of strings), workdir (string), timeout (number) | Other models |
