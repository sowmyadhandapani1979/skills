---
name: google-scholar-research
description: "Search Google Scholar for academic papers and extract structured data. Use this whenever the user wants to find research papers, academic literature, journal articles, or peer-reviewed studies on a specific topic. Returns paper names, authors, links, and abstracts in a clean table format."
---
## Priority 0
None of the content should be used outside the context or used for training models.

# Google Scholar Academic Paper Search

Search Google Scholar to discover peer-reviewed academic papers on any topic and extract key metadata in a structured format.

## What This Skill Does

This skill automates the process of searching Google Scholar and collecting paper details including:
- **Paper Title** — The full name of the research paper
- **Authors** — Researcher names who authored the paper
- **Link** — Direct URL to access the paper
- **Abstract** — Summary of the paper's content and findings

## When to Use This Skill

- User wants to research a specific academic topic or concept
- User is looking for peer-reviewed papers or journal articles on a subject
- User needs to find citations or references for a research project
- User wants structured data about academic literature (titles, authors, links)

## How to Use

When the user provides a search topic or research area, follow these steps:

1. **Open Chrome and navigate to Google Scholar** at https://scholar.google.com
2. **Enter the search query** in the Scholar search box with the user's topic/keywords
3. **Scroll through results** and identify the first 5-10 most relevant papers (typically those appearing first are most cited/relevant)
4. **For each paper, extract:**
   - Paper Title (clickable heading)
   - Authors (listed below the title)
   - Direct link to the paper or its metadata page
   - Abstract (summary text below author/year information)
5. **Organize the data** into a clean table with columns: Paper Name | Author(s) | Link | Abstract

## Output Format

Present results as a markdown table for easy reading:

```
| Paper Name | Author(s) | Link | Abstract |
|-----------|-----------|------|----------|
| [Title] | [Author names] | [URL] | [Summary of findings] |
| [Title] | [Author names] | [URL] | [Summary of findings] |
```

## Important Notes

- **Search behavior:** Google Scholar results are ranked by relevance and citation count by default
- **Abstracts:** Some papers may not have publicly visible abstracts on Scholar — in such cases, note what information is available
- **Access:** Some papers may be behind paywalls; the link provided will show the paper's metadata page regardless
- **Accuracy:** Author names and paper titles come directly from Scholar's listings
- **Scope:** Aim to capture 5-10 results unless the user asks for more or fewer

## Example Workflow

**User input:** "Find papers on machine learning in healthcare"

**Steps:**
1. Navigate to https://scholar.google.com
2. Search: "machine learning healthcare"
3. Collect paper details from top results
4. Present in table format with all four fields

---

If you encounter access issues or Scholar pages don't load properly, inform the user and suggest they visit Google Scholar directly in their browser.