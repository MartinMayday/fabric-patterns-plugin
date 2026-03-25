# Pattern Skill Template

Use this template to create new fabric-<pattern> skills.

## Quick Setup

```bash
# 1. Create skill directory
mkdir -p skills/fabric-PATTERN_NAME

# 2. Copy this template
cp templates/pattern-skill-template.md skills/fabric-PATTERN_NAME/SKILL.md

# 3. Edit the new skill file
# Replace PATTERN_NAME with actual pattern name
# Replace DESCRIPTION with pattern description

# 4. Add to fabric-patterns.local.md top_patterns list
```

---

## Template

```markdown
---
name: fabric-PATTERN_NAME
description: DESCRIPTION. TRIGGERS when user runs /fabric-PATTERN_NAME, says "use PATTERN_NAME pattern", or asks to apply PATTERN_NAME to content.
argument-hint: [source: URL, file, or text]
allowed-tools: Read, Grep, Bash
---

# PATTERN_NAME

Brief description of what this pattern does and when to use it.

## Behavior

When triggered:

1. **Identify source**:
   - YouTube URL → Extract transcript via yt-dlp
   - File path → Read file content
   - Web URL → Fetch content
   - Direct text → Use as-is

2. **Apply pattern**: Process content according to pattern requirements

3. **Output**: Format results in pattern-specific structure

## Pattern Definition

[Specific instructions for this pattern - what to extract, analyze, or create]

### Output Format

```
## Section 1
- Item 1
- Item 2

## Section 2
- Item 1
- Item 2

## Rating: X/10
[Brief justification]
```

## Examples

### YouTube Video
```
User: /fabric-PATTERN_NAME https://youtube.com/watch?v=abc123
Claude: [Extracts and processes YouTube content]
```

### Local File
```
User: /fabric-PATTERN_NAME ./notes/meeting.md
Claude: [Reads file and applies pattern]
```

### Direct Text
```
User: Apply PATTERN_NAME to this: [content]
Claude: [Processes provided text]
```

## Source Processing

Use fabric-core for extraction:
- YouTube: `yt-dlp` → transcript
- Files: `Read` tool → content
- URLs: `WebFetch`/`Firecrawl` → content
```

---

## Pattern Categories

Choose the right category for your pattern:

| Category | Purpose | Output Focus |
|----------|---------|--------------|
| **Extraction** | Pull specific info | Lists, items, data points |
| **Analysis** | Examine content | Findings, assessments, ratings |
| **Summarization** | Condense content | Concise overviews |
| **Creation** | Generate new content | Documents, code, artifacts |
| **Improvement** | Enhance existing content | Refined versions |
| **Security** | Security analysis | Threats, vulnerabilities, risks |

## Adding to Config

After creating the skill, add it to your top patterns:

Edit `fabric-patterns.local.md`:
```yaml
top_patterns:
  - PATTERN_NAME  # Add here
  - extract_wisdom
  - summarize
  # ...
```

## Testing

```bash
# Test the pattern
/fabric-PATTERN_NAME https://youtube.com/watch?v=test

# Verify output format matches expectations
# Check rating/quality assessment included
```
