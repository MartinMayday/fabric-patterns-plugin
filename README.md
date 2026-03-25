# Fabric Patterns Plugin

237 AI patterns from Daniel Miessler's Fabric, ready to use in Claude Code.

## Install

```shell
/plugin marketplace add MartinMayday/fabric-patterns-plugin
/plugin install fabric-patterns-plugin@fabric-patterns-plugin
```

Restart Claude Code after installing.

## Use

Skills auto-trigger when you ask naturally:

| Say | Result |
|-----|--------|
| "List fabric patterns" | Shows all 237 patterns |
| "Extract wisdom from [URL]" | Key insights & quotes |
| "Summarize [content]" | Concise summary |
| "Analyze threats in [content]" | Security assessment |
| "What's the main idea of [content]" | Core message |
| "Extract insights from [content]" | Non-obvious observations |
| "Rate the value of [content]" | 1-10 rating with justification |
| "Extract recommendations from [content]" | Actionable advice |

### Works With

- YouTube URLs → auto-extracts transcript
- Web URLs → fetches content
- Local files → reads directly
- Pasted text → processes immediately

## All 237 Patterns

| Category | Count | Examples |
|----------|-------|----------|
| Extraction | 40 | extract_wisdom, extract_insights, extract_predictions |
| Analysis | 35 | analyze_threat, analyze_risk, analyze_debate |
| Summarization | 15 | summarize, summarize_meeting, summarize_paper |
| Creation | 50 | create_keynote, create_prd, create_threat_model |
| Improvement | 10 | improve_writing, fix_typos, humanize |
| Security | 20 | create_threat_model, analyze_malware |

See `patterns/manifest.md` for complete list.

## Swap Patterns

The plugin includes 10 pre-built skills. To use a different pattern:

1. Find pattern name in `patterns/manifest.md`
2. Say: "Use the [pattern_name] pattern on [content]"

Example: "Use the create_keynote pattern on this article: [URL]"

## Requirements

- `yt-dlp` (YouTube extraction)
- Standard Unix tools (`awk`, `sed`)
