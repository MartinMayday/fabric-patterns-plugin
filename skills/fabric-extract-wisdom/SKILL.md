---
name: fabric-extract-wisdom
description: Extract wisdom, insights, lessons, and key takeaways from any content. TRIGGERS when user says "extract wisdom from", "what can I learn from", "key insights from", "wisdom from this", or runs /fabric-extract-wisdom.
argument-hint: [URL|file|text]
allowed-tools: [Read, Bash]
---

# Extract Wisdom Pattern

Extract key wisdom, insights, and lessons from content.

## Trigger Phrases

- "Extract wisdom from this..."
- "What can I learn from..."
- "Key insights from..."
- "Wisdom from this video/article/file"
- `/fabric-extract-wisdom [source]`

## Behavior

When triggered:

1. **Identify source**:
   - YouTube URL → Extract transcript
   - File path → Read file
   - Web URL → Fetch content
   - Text → Process directly

2. **Extract wisdom** using this framework:

```
## Summary
[One sentence summary of the content]

## Key Insights
- [Insight 1]
- [Insight 2]
- [Insight 3]

## Lessons Learned
- [Lesson 1]
- [Lesson 2]

## Quotes
> "[Notable quote 1]"
> "[Notable quote 2]"

## Recommendations
- [Recommendation 1]
- [Recommendation 2]

## Rating
[How valuable/useful is this content? 1-10]
```

## Examples

### YouTube Video
```
User: /fabric-extract-wisdom https://youtube.com/watch?v=abc123

Claude:
## Summary
Video about building sustainable habits through small incremental changes.

## Key Insights
- Habits form through consistency, not intensity
- Identity-based habits outperform outcome-based goals
- Environment design is more effective than willpower

## Lessons Learned
- Start with changes so small they seem trivial
- Focus on who you want to become, not what you want to achieve
- Design your environment to make good choices easier

## Quotes
> "You do not rise to the level of your goals. You fall to the level of your systems."
> "Every action you take is a vote for the type of person you wish to become."

## Recommendations
- Apply the 2-minute rule to start any habit
- Use habit stacking to link new habits to existing ones

## Rating: 8/10
Practical, actionable wisdom with clear examples.
```

### Text/File
```
User: Extract wisdom from this text: [pasted content]

Claude: [Extracts wisdom from the provided text]
```

### Local File
```
User: /fabric-extract-wisdom ./notes/meeting.md

Claude: [Reads file and extracts wisdom]
```

## Source Processing

### YouTube
```bash
URL="[provided-url]"
yt-dlp --restrict-filenames --write-auto-sub --sub-lang en --skip-download \
  --sub-format srt --output "transcripts/%(title)s/%(title)s-%(uploader)s" "$URL"
# Convert SRT to text, then apply wisdom extraction
```

### File
```bash
# Read file content
Read "./path/to/file"
# Apply wisdom extraction to content
```

### URL
```bash
# Fetch web content
# Apply wisdom extraction to fetched content
```

## Quality Standards

- Identify 3-7 key insights (not too few, not too many)
- Include at least 2 direct quotes when available
- Provide actionable recommendations
- Give honest rating with justification
