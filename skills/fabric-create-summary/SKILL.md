---
name: fabric-create-summary
description: Create comprehensive summaries with multiple depth levels. TRIGGERS when user says "create a detailed summary", "comprehensive summary", "multi-level summary", or runs /fabric-create-summary.
argument-hint: [source: URL, file path, or text]
allowed-tools: Read, Grep, Bash, WebFetch
---

# Create Summary

Generate a comprehensive, multi-level summary with short, medium, and long versions.

## Behavior

1. **Identify source**:
   - URL/File/Text → Extract content

2. **Create three summary levels**:
   - **One-liner**: Single sentence essence
   - **Paragraph**: 3-5 sentence overview
   - **Detailed**: Full comprehensive summary

3. **Include structure elements**:
   - Key themes
   - Important quotes
   - Action items (if applicable)

## Output Format

```
## Summary: [Title]

### One-Liner
[The entire content in one sentence]

### Paragraph Summary
[3-5 sentences capturing the essential narrative/argument]

### Detailed Summary

#### Context
[Brief setup and background]

#### Main Content
[Comprehensive summary of core material]

#### Key Points
1. [Important point with supporting detail]
2. [Important point with supporting detail]
3. [Important point with supporting detail]
4. [Important point with supporting detail]

#### Notable Quotes
> "[Direct quote 1]"
> "[Direct quote 2]"

#### Themes
- [Theme 1]
- [Theme 2]
- [Theme 3]

#### Action Items (if applicable)
- [ ] [Action 1]
- [ ] [Action 2]

---
Stats: [X] words from [Y] source words ([Z]% compression)
```

## Examples

### YouTube Video
```
User: /fabric-create-summary https://youtube.com/watch?v=abc123

Claude: [Creates multi-level summary with all sections]
```

### Meeting Notes
```
User: Create a detailed summary of this meeting: [notes]

Claude:
## Summary: Q4 Planning Meeting

### One-Liner
Team aligned on three major initiatives for Q4 with focus on customer retention and platform stability.

### Paragraph Summary
The Q4 planning session resulted in consensus on three priority initiatives: improving customer onboarding, reducing platform latency by 40%, and launching the enterprise tier. Budget allocations were approved for two additional engineers and one product manager. Key concerns included timeline risks and cross-team coordination.

### Detailed Summary
[Full detailed summary follows]
```

### Document
```
User: /fabric-create-summary ./reports/analysis.md

Claude: [Creates comprehensive summary]
```

## Quality Standards

- All three levels must be internally consistent
- Shorter versions should be accurate reflections
- Include specific details in detailed version
- Capture both facts and implications
- Note any uncertainties or gaps
