---
name: fabric-extract-insights
description: Extract key insights and non-obvious observations from content. TRIGGERS when user says "extract insights", "what are the insights", "key takeaways", or runs /fabric-extract-insights.
argument-hint: [source: URL, file, or text]
allowed-tools: Read, Grep, Bash, WebFetch
---

# Extract Insights

Identify non-obvious observations, surprising connections, and valuable insights from content.

## Behavior

1. **Extract content** from YouTube, file, URL, or text
2. **Find insights** that are:
   - Non-obvious (not immediately apparent)
   - Actionable (can be applied)
   - Surprising (contradict common assumptions)
   - Connected (link to broader patterns)

## Output Format

```
## Insights: [Title]

### Surprising Observations
1. **[Observation]**: [Why it's surprising]
2. **[Observation]**: [Why it's surprising]

### Non-Obvious Connections
- [Connection between ideas that isn't immediately obvious]
- [Pattern that emerges when looking at the full picture]

### Actionable Insights
| Insight | Application |
|---------|--------------|
| [Insight 1] | How to apply this |
| [Insight 2] | How to apply this |

### Counter-Intuitive Findings
- [What most people think vs. what's actually true]

---
Total insights: [X]
```

## Example

```
User: Extract insights from https://youtube.com/watch?v=abc123

Claude:
## Insights: Atomic Habits Research

### Surprising Observations
1. **Identity beats outcomes**: Focusing on who you want to become is 3x more effective than focusing on what you want to achieve
2. **Environment > Willpower**: People with good environments succeed 80% more than those relying on self-control

### Non-Obvious Connections
- Habit formation and addiction recovery use the same neural pathways
- The 2-minute rule works because it bypasses the brain's resistance to change

### Actionable Insights
| Insight | Application |
|---------|--------------|
| Habit stacking | Attach new habits to existing ones for 50% higher success |
| Environment design | Remove friction from good habits, add friction to bad ones |

---
Total insights: 7
```
