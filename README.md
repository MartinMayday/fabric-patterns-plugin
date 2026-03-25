# Fabric Patterns Plugin

Daniel Miessler's Fabric patterns as native Claude Code skills.

## Installation

```bash
# Clone or copy to your plugins directory
git clone https://github.com/YOUR_USERNAME/fabric-patterns-plugin.git
claude-code --plugin-dir ./fabric-patterns-plugin
```

Or add to your settings.json:
```json
{
  "plugins": ["~/path/to/fabric-patterns-plugin"]
}
```

## Available Commands

| Command | Description |
|---------|-------------|
| `/fabric-list` | List all 237 patterns (top N + full catalog) |
| `/fabric-list --top 5` | Show top 5 patterns |
| `/fabric-list --search threat` | Search patterns |
| `/fabric-extract-wisdom [source]` | Extract wisdom from content |
| `/fabric-summarize [source]` | Summarize content |
| `/fabric-analyze-threat [source]` | Analyze security threats |
| ... | (based on top_patterns config) |

## Configuration

Edit `fabric-patterns.local.md`:

```yaml
---
top_count: 10
default_pattern: extract_wisdom
top_patterns:
  - extract_wisdom
  - summarize
  - analyze_threat
  - extract_main_idea
  - create_summary
  - extract_recommendations
  - rate_value
  - extract_insights
  - create_keynote
  - analyze_memoir
---
```

### Adding New Patterns

1. Find pattern name in `patterns/manifest.md`
2. Add to `top_patterns` list in config
3. Create skill file:

```bash
mkdir -p skills/fabric-PATTERN_NAME
```

Create `skills/fabric-PATTERN_NAME/SKILL.md`:
```markdown
---
name: fabric-PATTERN_NAME
description: [Description]. TRIGGERS when user runs /fabric-PATTERN_NAME
argument-hint: [source: URL, file path, or text]
allowed-tools: Read, Grep, Bash
---

# Pattern Name

Brief description of what this pattern does.

## Behavior

[Pattern-specific instructions]

## Examples

User: /fabric-PATTERN_NAME https://youtube.com/...
Claude: [Applies pattern to YouTube video]
```

## Input Sources

All patterns accept:

- **YouTube URLs**: `https://youtube.com/watch?v=...`
- **Local files**: `./path/to/file.md`
- **Web URLs**: `https://example.com/article`
- **Direct text**: Paste content directly

## Pattern Categories

| Category | Count | Examples |
|----------|-------|----------|
| Extraction | 40 | extract_wisdom, extract_insights |
| Analysis | 35 | analyze_threat, analyze_risk |
| Summarization | 15 | summarize, summarize_meeting |
| Creation | 50 | create_keynote, create_prd |
| Improvement | 10 | improve_writing, fix_typos |
| Security | 20 | create_threat_model, analyze_malware |

See `patterns/manifest.md` for the complete list of 237 patterns.

## Dependencies

- `yt-dlp` for YouTube extraction
- Standard Unix tools: `awk`, `sed`

## Credits

Patterns from [Daniel Miessler's Fabric](https://github.com/danielmiessler/fabric) project.
