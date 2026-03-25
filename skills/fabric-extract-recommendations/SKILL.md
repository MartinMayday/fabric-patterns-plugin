---
name: fabric-extract-recommendations
description: Extract actionable recommendations and advice from content. TRIGGERS when user says "extract recommendations", "what should I do", "action items from", or runs /fabric-extract-recommendations.
argument-hint: [source: URL, file, or text]
allowed-tools: Read, Grep, Bash, WebFetch
---

# Extract Recommendations

Pull out all actionable recommendations, advice, and suggested actions from content.

## Behavior

1. **Extract content** from source
2. **Identify all recommendations**:
   - Explicit advice ("you should...")
   - Implied suggestions ("consider...")
   - Lessons learned ("what worked was...")
3. **Prioritize by impact and actionability**

## Output Format

```
## Recommendations: [Title]

### Immediate Actions (Do Today)
- [ ] [Action 1]
- [ ] [Action 2]

### Short-Term (This Week)
- [ ] [Action 1]
- [ ] [Action 2]

### Long-Term Changes
- [ ] [Change 1]
- [ ] [Change 2]

### Conditional Recommendations
**If [condition]**: [recommendation]
**If [condition]**: [recommendation]

### Top 3 Priority Actions
1. **[Most important]**: [Why it matters]
2. **[Second most]**: [Why it matters]
3. **[Third most]**: [Why it matters]

---
Total recommendations: [X]
```

## Example

```
User: Extract recommendations from https://youtube.com/watch?v=abc123

Claude:
## Recommendations: Atomic Habits

### Immediate Actions (Do Today)
- [ ] Pick one habit to focus on (not multiple)
- [ ] Reduce it to a 2-minute version
- [ ] Attach it to an existing habit

### Short-Term (This Week)
- [ ] Redesign your environment to support the habit
- [ ] Create a habit tracking system
- [ ] Identity statement: "I am a person who..."

### Long-Term Changes
- [ ] Build systems instead of setting goals
- [ ] Regular environment audits
- [ ] Quarterly habit reviews

### Top 3 Priority Actions
1. **Start with 2-minute version**: Overcomes initial resistance
2. **Stack on existing habit**: Uses existing neural pathways
3. **Design environment first**: More reliable than willpower

---
Total recommendations: 12
```
