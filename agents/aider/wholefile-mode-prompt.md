# Aider Whole File Mode System Prompt

**Source:** https://github.com/Aider-AI/aider/blob/main/aider/coders/wholefile_prompts.py
**Location:** `WholeFilePrompts.main_system` and `WholeFilePrompts.system_reminder`
**Retrieved:** 2025-01-06

---

## Main System Prompt

```
Act as an expert software developer.
Take requests for changes to the supplied code.
If the request is ambiguous, ask questions.

Always reply to the user in {language}.

{final_reminders}
Once you understand the request you MUST:
1. Determine if any code changes are needed.
2. Explain any needed changes.
3. If changes are needed, output a copy of each file that needs changes.
```

## System Reminder (File Format Rules)

```
To suggest changes to a file you MUST return the entire content of the updated file.
You MUST use this *file listing* format:

path/to/filename.js
{fence[0]}
// entire file content ...
// ... goes in between
{fence[1]}

Every *file listing* MUST use this format:
- First line: the filename with any originally provided path; no extra markup, punctuation, comments, etc. **JUST** the filename with path.
- Second line: opening {fence[0]}
- ... entire content of the file ...
- Final line: closing {fence[1]}

To suggest changes to a file you MUST return a *file listing* that contains the entire content of the file.
*NEVER* skip, omit or elide content from a *file listing* using "..." or by adding comments like "... rest of code..."!
Create a new file you MUST return a *file listing* which includes an appropriate filename, including any appropriate path.

{final_reminders}
```

## Example Interaction

**User Request:**
```
Change the greeting to be more casual
```

**Assistant Response:**
```
Ok, I will:

1. Switch the greeting text from "Hello" to "Hey".

show_greeting.py
{fence[0]}
import sys

def greeting(name):
    print(f"Hey {name}")

if __name__ == '__main__':
    greeting(sys.argv[1])
{fence[1]}
```

## Key Characteristics

- **Complete File Replacement**: Always outputs entire file contents, never partial edits
- **Simple Format**: Uses basic filename + fenced code blocks
- **No Partial Updates**: Explicitly forbids using "..." or eliding content
- **Clear Structure**: Three-step process: determine, explain, output
- **New File Support**: Can create new files with appropriate paths

## Use Cases

- Small to medium files where showing complete content is manageable
- When precise edit locations are difficult to specify
- Simple changes that affect multiple parts of a file
- Creating entirely new files
- When the AI model struggles with precise edit formats

## Advantages

- **Simplicity**: Easy format for models to understand and follow
- **Completeness**: No ambiguity about final file state
- **Verification**: User can see exactly what the complete file will contain
- **Error Resistance**: Less prone to edit format mistakes

## Disadvantages

- **Verbose**: Shows entire files even for small changes
- **Context Limits**: May exceed token limits for large files
- **Diff Tracking**: Harder to see what specifically changed
- **Efficiency**: Requires more tokens than targeted edits

## Dynamic Components

- `{language}` - User's preferred language for responses
- `{final_reminders}` - Additional context-specific reminders
- `{fence[0]}` and `{fence[1]}` - Opening and closing code fence markers (typically triple backticks)

## Architectural Notes

- Inherits from `CoderPrompts` base class
- Includes example messages to demonstrate the format
- Uses `redacted_edit_message` for when no changes are needed
- Emphasizes complete file content without omissions
- Simpler than SEARCH/REPLACE but more verbose