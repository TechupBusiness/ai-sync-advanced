---
name: research
description: Conduct research with up-to-date information via aichat CLI. Use when you need current information, real-time data, or need to research topics beyond your knowledge cutoff.
version: 1.0.0
allowed-tools: Bash

---

# AI Research Skill

Use `aichat` to query Grok and Perplexity for real-time web research.

## When to Use

This skill should be used when:
- You need current/real-time information beyond your knowledge cutoff
- Researching library APIs, software features, or documentation
- Verifying facts or getting up-to-date data
- User explicitly asks for web research

## Models

| Model | Flag | Speed | Use For |
|-------|------|-------|---------|
| Grok 4.1 Fast | `-m openrouter:x-ai/grok-4.1-fast` | 4-6s | Quick answers, iteration |
| Perplexity Deep | `-m openrouter:perplexity/sonar-deep-research` | 20-40s | Comprehensive analysis, citations |

## Instructions

### Quick Research (4-6 sec)

```bash
aichat -m openrouter:x-ai/grok-4.1-fast "your research question"
```

### Deep Research (20-40 sec)

```bash
aichat -m openrouter:perplexity/sonar-deep-research "your research question"
```

### Parallel Research (Recommended)

Run both models in parallel for comprehensive results:

```bash
aichat -m openrouter:x-ai/grok-4.1-fast "What are the latest React 19 features?" &
aichat -m openrouter:perplexity/sonar-deep-research "What are the latest React 19 features?" &
wait
```

### Save Output

```bash
aichat -m openrouter:x-ai/grok-4.1-fast "Research topic" > research.md
```

## Best Practices

- Run both models in parallel - Grok for speed, Perplexity for depth
- Include "provide sources" in your query for citations
- Be specific in your questions for better results
- For API documentation, ask for "official documentation" or "latest version"
