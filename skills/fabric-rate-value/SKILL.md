---
name: fabric-rate-value
description: Rate the value of content on a scale of 1-10 with justification. TRIGGERS when user says "rate this", "how valuable is this", "rate value", or runs /fabric-rate-value.
argument-hint: [source: URL, file, or text]
allowed-tools: Read, Grep, Bash, WebFetch
---

# Rate Value

Assess the practical value of content and provide a justified rating.

## Behavior

1. **Extract content** from source
2. **Evaluate on multiple dimensions**:
   - Actionability (can you use it?)
   - Novelty (is it new information?)
   - Credibility (is it trustworthy?)
   - Applicability (how broadly does it apply?)
   - Depth (how thorough is it?)

## Output Format

```
## Value Rating: [X]/10

### Quick Verdict
[One sentence: worth your time or not?]

### Rating Breakdown

| Dimension | Score | Reason |
|-----------|-------|--------|
| Actionability | [1-10] | [Why] |
| Novelty | [1-10] | [Why] |
| Credibility | [1-10] | [Why] |
| Applicability | [1-10] | [Why] |
| Depth | [1-10] | [Why] |
| **Overall** | **[X]/10** | |

### Who Should Consume This
- [Target audience 1]
- [Target audience 2]

### Value Highlights
- [Most valuable point]
- [Second most valuable point]

### Red Flags / Weaknesses
- [Issue 1]
- [Issue 2]

### Bottom Line
[2-3 sentences: should you spend time on this?]
```

## Example

```
User: Rate the value of this video: https://youtube.com/watch?v=abc123

Claude:
## Value Rating: 8/10

### Quick Verdict
Highly practical for anyone building habits, with actionable frameworks backed by research.

### Rating Breakdown

| Dimension | Score | Reason |
|-----------|-------|--------|
| Actionability | 9 | Every concept has a clear implementation method |
| Novelty | 7 | Some ideas are well-known, but synthesis is fresh |
| Credibility | 9 | Backed by studies and real-world testing |
| Applicability | 9 | Applies to virtually everyone |
| Depth | 7 | Good depth but some surface-level examples |

### Who Should Consume This
- People struggling to build consistent habits
- Coaches and therapists working on behavior change
- Product managers designing habit-forming products

### Bottom Line
Worth 45 minutes if you're serious about behavior change. Skip the first 10 minutes if you know the basics.
```
