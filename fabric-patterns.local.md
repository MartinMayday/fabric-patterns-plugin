---
# Fabric Patterns Plugin Configuration
# Edit this file to customize your top patterns and defaults

top_count: 10
default_pattern: extract_wisdom

# These patterns appear as /fabric-<name> commands
# Change the order to change which appear first
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

# All available patterns (200+) are listed in patterns/manifest.md
# To add a new pattern to your top list:
# 1. Copy pattern name from patterns/manifest.md
# 2. Add it to top_patterns above
# 3. Create skills/fabric-<pattern-name>/SKILL.md
---

# Fabric Patterns Configuration

This file configures which Fabric patterns appear as slash commands.

## Settings

- `top_count`: Number of patterns to show in "top" section of /fabric-list
- `default_pattern`: Pattern used when none specified
- `top_patterns`: Patterns that get /fabric-<name> commands

## Adding New Patterns

1. Browse all patterns in `patterns/manifest.md`
2. Add the pattern name to `top_patterns` above
3. Create a new skill: `skills/fabric-<pattern>/SKILL.md`
4. Use the template from `skills/fabric-extract-wisdom/SKILL.md`

## Example

To add `analyze_debate` to your top patterns:

```yaml
top_patterns:
  - extract_wisdom
  - analyze_debate  # Added
  - summarize
  ...
```

Then create `skills/fabric-analyze-debate/SKILL.md` using the template.
