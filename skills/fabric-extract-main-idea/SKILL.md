---
name: fabric-extract-main-idea
description: Extract the single most important concept or message from content. TRIGGERS when user says "what's the main idea", "extract the core message", "main point", or runs /fabric-extract-main-idea.
argument-hint: [source: URL, file path, or text]
allowed-tools: Read, Grep, Bash, WebFetch
---

# Extract Main Idea

Identify and articulate the single most important concept from content.

## Behavior

1. **Identify source**:
   - URL/File/Text → Extract content

2. **Find the core message**:
   - What is the author really trying to say?
   - What would be lost if everything else was removed?
   - What's the non-negotiable central point?

3. **Express in one clear statement**

## Output Format

```
## Main Idea: [Title]

### The Core Message
[One paragraph (2-4 sentences) stating the main idea clearly]

### Why This Matters
[Why this idea is significant - context and implications]

### Supporting Points
- [Point that supports main idea]
- [Point that supports main idea]
- [Point that supports main idea]

### In One Sentence
[The entire content distilled to a single sentence]

---
Confidence: [High/Medium/Low]
```

## Examples

### YouTube Video
```
User: /fabric-extract-main-idea https://youtube.com/watch?v=abc123

Claude:
## Main Idea: Building Atomic Habits

### The Core Message
Sustainable personal change comes not from dramatic transformations but from tiny, consistent improvements that compound over time. The most effective approach combines identity-based goals (who you want to become) with environment design that makes good choices automatic rather than requiring willpower.

### Why This Matters
Most self-improvement efforts fail because they rely on motivation and willpower, which are finite resources. Understanding that systems and environment beat willpower changes how we approach all behavior change.

### Supporting Points
- 1% improvements compound to 37x improvement in a year
- Focus on identity ("I am a runner") not outcomes ("I want to run a marathon")
- Design your environment to make good choices the path of least resistance

### In One Sentence
Small, consistent actions that align with your desired identity will transform your life more than any dramatic resolution or burst of motivation.

---
Confidence: High
```

### Article
```
User: What's the main idea of this article? [content]

Claude: [Extracts core message]
```

## Quality Standards

- Must be expressible in ONE sentence
- Should be "sticky" - memorable and quotable
- Distinct from just summarizing - find the essence
- If multiple main ideas exist, acknowledge tension
