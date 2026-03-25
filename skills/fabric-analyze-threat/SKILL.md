---
name: fabric-analyze-threat
description: Analyze content for security threats, risks, and vulnerabilities. TRIGGERS when user says "analyze threats", "security analysis", "threat assessment", or runs /fabric-analyze-threat.
argument-hint: [source: URL, file path, or text]
allowed-tools: Read, Grep, Bash, WebFetch
---

# Analyze Threat

Perform security-focused analysis to identify threats, vulnerabilities, and risks.

## Behavior

1. **Identify source**:
   - URL/File/Text → Extract content
   - Focus on security-relevant elements

2. **Analyze for**:
   - Threat actors and motivations
   - Attack vectors and methods
   - Vulnerabilities and weaknesses
   - Impact and severity
   - Mitigation recommendations

3. **Provide actionable** security assessment

## Output Format

```
## Threat Analysis: [Subject]

### Executive Summary
[2-3 sentence overview of threat landscape]

### Identified Threats

| Threat | Severity | Likelihood | Impact |
|--------|----------|------------|--------|
| [Threat 1] | Critical/High/Medium/Low | High/Med/Low | [Description] |
| [Threat 2] | ... | ... | ... |

### Attack Vectors
1. **[Vector 1]**: [Description]
   - Prerequisites: [What attacker needs]
   - Impact: [What attacker achieves]
   - Detection: [How to detect]

### Vulnerabilities
- **[Vuln 1]**: [Description and exploitation potential]
- **[Vuln 2]**: [Description and exploitation potential]

### Recommendations
1. **Immediate**: [Critical actions]
2. **Short-term**: [Important improvements]
3. **Long-term**: [Strategic security enhancements]

### Risk Rating: [X]/10
[Justification for rating]
```

## Examples

### Security Report
```
User: /fabric-analyze-threat https://example.com/security-report.pdf

Claude: [Analyzes PDF for threat intelligence]
```

### Code Review
```
User: Analyze threats in this code: [code snippet]

Claude: [Identifies security vulnerabilities]
```

### Threat Intel
```
User: /fabric-analyze-threat ./intel/threat-report.md

Claude: [Extracts and analyzes threat information]
```

## Focus Areas

- Data exfiltration risks
- Authentication/authorization flaws
- Injection vulnerabilities
- Misconfigurations
- Social engineering indicators
- Malware/IOC signatures
- Supply chain risks
