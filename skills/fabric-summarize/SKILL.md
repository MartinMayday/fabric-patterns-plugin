---
name: fabric-summarize
description: Create concise, accurate summaries of any content. TRIGGERS when user says "summarize this", "create summary", "give me a summary", or runs /fabric-summarize.
argument-hint: [source: URL, file path, or text]
allowed-tools: Read, Grep, Bash, WebFetch
---

# Summarize

Create a clear, concise summary that captures the essential information.

## Behavior

1. **Identify source**:
   - YouTube URL → Extract transcript
   - File path → Read file
   - Web URL → Fetch content
   - Direct text → Use as-is

2. **Create summary** with:
   - One-sentence essence
   - 3-5 key points
   - Main takeaway

3. **Keep it concise** - Aim for 10-20% of original length

## Output Format

```
## Summary: [Title/Topic]

**One-sentence essence**: [Core message in one sentence]

### Key Points
1. [First key point]
2. [Second key point]
3. [Third key point]
4. [Fourth key point]
5. [Fifth key point]

### Main Takeaway
[The single most important thing to remember]

---
Length: [X] words (from [Y] original - [Z]% compression)
```

## Examples

### YouTube Video
```
User: /fabric-summarize https://youtube.com/watch?v=abc123

Claude:
## Summary: Atomic Habits - Building Small Changes

**One-sentence essence**: Sustainable behavior change comes from small, consistent actions rather than dramatic overhauls.

### Key Points
1. 1% improvements compound dramatically over time
2. Identity-based habits beat outcome-based goals
3. Environment design trumps willpower
4. Habit stacking links new behaviors to existing ones
5. The 2-minute rule makes starting effortless

### Main Takeaway
Focus on becoming the type of person who does the habit, not on achieving a specific outcome.

---
Length: 85 words (from 4,200 original - 98% compression)
```

### Article
```
User: /fabric-summarize https://blog.example.com/article

Claude: [Creates concise summary]
```

### File
```
User: /fabric-summarize ./notes/meeting.md

Claude: [Summarizes meeting notes]
```

## Quality Standards

- Capture essence in first sentence
- Prioritize most important points
- Use clear, simple language
- Include actionable takeaways
- Show compression ratio
