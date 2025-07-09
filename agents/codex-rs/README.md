# Codex CLI (Rust) System Prompt

[Codex CLI](https://github.com/openai/codex) is OpenAI's Rust-implemented command-line coding assistant that uses a specialized patch-based system for code modification and execution.

## System Prompts

- **[system-prompt.md](system-prompt.md)** - Complete system prompt with coding guidelines and patch-based editing instructions

## Tools

- **local_shell** - Provides access to shell environment with specialized `apply_patch` command

## Key Features

- **Patch-Based Editing**: Uses specialized `apply_patch` command for safe file modifications
- **Performance Optimized**: Uses `rg` (ripgrep) instead of slower search tools

## Patch System

The agent uses a specialized patch language with three main operations:
- `Add File`: Create new files
- `Update File`: Modify existing files (with optional renaming)
- `Delete File`: Remove files

The patch format is designed to be safe, parseable, and easy to apply programmatically.
