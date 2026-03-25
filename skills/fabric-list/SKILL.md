---
name: fabric-list
description: List all available Fabric patterns with descriptions. TRIGGERS when user asks "what patterns are available", "list fabric patterns", "show patterns", "fabric patterns list", or runs /fabric-list.
argument-hint: [--top N] [--search TERM]
allowed-tools: [Read]
---

# List Fabric Patterns

Display available Fabric patterns from the manifest.

## Behavior

When invoked as `/fabric-list`:

1. **Load configuration** from `fabric-patterns.local.md`:
   - `top_count` (default: 10)
   - `top_patterns` list

2. **Load manifest** from `patterns/manifest.md`

3. **Display output** in two sections:

```
## Top 10 Patterns (Configured)

| Pattern | Description |
|---------|-------------|
| extract_wisdom | Extract key wisdom and insights |
| summarize | Create concise summary |
| ... | ... |

## All 237 Patterns

### Extraction (40 patterns)
- extract_wisdom
- extract_main_idea
- ...

### Analysis (35 patterns)
- analyze_threat
- analyze_risk
- ...

### Summarization (15 patterns)
- summarize
- summarize_meeting
- ...

### Creation (50 patterns)
- create_keynote
- create_prd
- ...

### And more...
```

## Arguments

### `--top N`
Change how many patterns appear in "Top" section.

```
/fabric-list --top 5
```

Shows top 5 instead of configured default.

### `--search TERM`
Search patterns by name or description.

```
/fabric-list --search threat
```

Shows only patterns matching "threat":
```
## Patterns matching "threat" (8 found)

| Pattern | Description |
|---------|-------------|
| analyze_threat | Analyze security threats |
| analyze_threat_report | Analyze threat reports |
| create_threat_model | Create threat models |
| create_threat_scenarios | Create threat scenarios |
| create_stride_threat_model | STRIDE modeling |
| ...
```

## Configuration

Edit `fabric-patterns.local.md` to change defaults:

```yaml
top_count: 10
top_patterns:
  - extract_wisdom
  - summarize
  - analyze_threat
  # Add more patterns here
```

## Example Usage

```
User: /fabric-list
Claude: [Shows top 10 + all patterns]

User: /fabric-list --top 5
Claude: [Shows top 5 + all patterns]

User: /fabric-list --search video
Claude: [Shows video-related patterns]

User: what patterns are available for security analysis?
Claude: [Shows security-related patterns]
```
