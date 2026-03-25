---
name: fabric-core
description: Core content extraction and processing engine for Fabric patterns. Used internally by all fabric-<pattern> skills. Handles YouTube videos, local files, web URLs, and text input.
---

# Fabric Core Engine

**Internal skill** - Used by all fabric-<pattern> skills. Do not invoke directly.

## Input Sources

This skill processes content from multiple sources:

### 1. YouTube Videos
```bash
yt-dlp --restrict-filenames --write-auto-sub --sub-lang en --skip-download \
  --sub-format srt --output "transcripts/%(title)s/%(title)s-%(uploader)s" "$URL"

# Convert SRT to text with timestamps
awk '/^[0-9]+$/{next}/-->/{split($1,s,",");t=substr(s[1],1,8);next}/^[[:space:]]*$/{next}{gsub(/&#39;/,"'"'"'",$0);print"["t"] "$0}' "$SRT_FILE"
```

### 2. Local Files
- PDF: Use Read tool to extract text
- Markdown/Text: Use Read tool directly
- Code: Use Read tool directly

### 3. Web URLs
- Use Firecrawl MCP or WebFetch to extract content
- Fallback to Read tool for raw HTML

### 4. Direct Text
- Process text content directly

## Processing Pipeline

1. **Extract**: Get content from source
2. **Clean**: Remove artifacts, normalize formatting
3. **Process**: Apply pattern-specific analysis
4. **Format**: Output in requested format

## Pattern Application

Each fabric-<pattern> skill provides:
- Pattern-specific system prompt
- Input/output format requirements
- Processing instructions

The core engine handles:
- Source detection and extraction
- Content normalization
- Error handling
- Result caching (optional)

## Output Formats

Patterns can output:
- Plain text (default)
- Markdown
- JSON (structured)
- Tables
- Bullet lists

## Error Handling

| Error | Action |
|-------|--------|
| No subtitles | Fall back to description/metadata |
| Private video | Report error, suggest alternatives |
| File not found | Clear error message |
| URL unreachable | Suggest alternative sources |

## Usage by Pattern Skills

Pattern skills call this core via:
```
1. Extract content using appropriate method
2. Apply pattern prompt to extracted content
3. Return formatted output
```

## Dependencies

- `yt-dlp`: YouTube/video extraction
- `awk`: Text processing
- `Read` tool: File access
- `Firecrawl`/`WebFetch`: Web content
