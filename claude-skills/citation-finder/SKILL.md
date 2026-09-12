---
name: citation-finder
description: Enrich academic paragraphs with relevant citations automatically. Provide any research content and this skill identifies 0-2 most relevant citations per sentence using context-aware semantic search on Google Scholar, then embeds them textually with IEEE-formatted references. Use when writing papers, enriching literature reviews, validating research claims, or adding citations to academic content.
compatibility: Chrome connector for Google Scholar access
---

# Citation Finder

Automatically enrich academic paragraphs with relevant citations.

## Execution

Process input immediately. No questions. No clarification requests.

1. Accept paragraph input as-is
2. Analyze overall theme and argument
3. Parse sentences and extract semantic meaning
4. Construct context-aligned Google Scholar queries
5. Search and evaluate relevance
6. Select 0-2 citations per sentence
7. Embed citations textually before full-stops
8. Format references in IEEE style (no DOI)
9. Return enriched text with References section

## Output Format

**Text with embedded citations:**
```
...processing, as described in [1]. The organization understands impact, as noted in [2].
```

**IEEE References:**
```
[1] B. E. Ashforth and F. Mael, "Social identity theory and the organization," 
    Academy of Management Review, vol. 14, no. 1, pp. 20–39, 1989.

[2] F. Mael and L. E. Tetrick, "Identifying organizational identification," 
    Educational and Psychological Measurement, vol. 52, no. 4, pp. 813–824, 1992.
```

## Citation Format

```
[#] First Initial. Last Name and First Initial. Last Name, "Article title," 
    Journal Name, vol. #, no. #, pp. page–page, year.
```

## Search Strategy

- Understand paragraph theme before searching
- Match citations to conceptual meaning, not just keywords
- Construct context-aligned queries
- Prioritize recent papers (10-15 years) unless foundational works more relevant
- Only include papers with accessible links or DOI numbers
- Return 0 citations if no relevant matches exist

## Quality Standards

- Citation has verifiable link or DOI
- Publication year and venue are credible
- Content relevance to sentence is high
- No duplicate citations
- 0-2 citations per sentence (0 acceptable)

## When to Use

- Academic paper writing
- Adding references to research content
- Validating research claims
- Enriching literature review sections
- Citation management for multi-paragraph content

**Execute without asking questions. Process input autonomously. Return results immediately.**
