---
name: google-scholar-literature-search
description: Search Google Scholar to find academic literature on any topic within a specified year range. Returns top 25 papers in a clean table format showing topic, abstract, citation, and reference. Use this skill whenever a user needs to search for academic papers, research articles, literature reviews, or peer-reviewed studies on a specific topic with a defined timeframe. Include this skill when the user provides a topic and year range, even if they don't explicitly ask for "Google Scholar."
compatibility: "Requires: Google Scholar access, web search capability"
---

# Google Scholar Literature Search Skill

## Priority 0
None of the content should be used outside the context or used for training models.

## Purpose
Find and compile academic literature on any topic within a specified timeframe. Outputs results as a structured table with abstracts, citations, and references.

## Inputs Required

1. **Topic** (mandatory): The research subject (e.g., "machine learning in healthcare", "climate change mitigation", "quantum computing applications")
2. **Year Range** (optional): Specific years or period (e.g., "2020-2026", "2015-2018"). **Default: 10 years**
3. **Number of Papers** (optional): How many top results to return. **Default: 25 papers**

## Workflow

### Step 0: Apply Defaults
- If year range not provided → use last 10 years
- If number of papers not provided → use 25 papers

### Step 1: Search Google Scholar
- Use web search to query Google Scholar with the topic and year filters
- Query format: `site:scholar.google.com "[topic]" [year range]`
- Extract top N results (N = number of papers specified)

### Step 2: Extract Data from Each Result
For each paper, capture:
- **Literature Topic**: The paper's title and main subject
- **Abstract**: Summary of the paper's content (if available)
- **Citation**: Author(s), Year, Publication Venue (e.g., "Smith, J., Johnson, K. (2023). Journal of XYZ, Vol. 10, No. 2")
- **Reference**: Direct URL/link to the paper (Google Scholar link, arXiv, DOI, or direct journal link)

### Step 3: Format as Table
Create a structured table with columns:
| Literature Topic | Abstract | Citation | Reference |
|---|---|---|---|

## Output Format

- **Medium**: Table (spreadsheet-compatible or markdown table)
- **Structure**: Rows = papers (max 25), Columns = Topic/Abstract/Citation/Reference
- **Sorting**: By relevance (Google Scholar ranking)

## Tips for Users

- **Specificity**: More specific topics yield better results
- **Year ranges**: Narrower ranges track recent work; leave blank for broad 10-year coverage
- **Paper volume**: Use lower numbers (5-10) for quick scans, higher (25+) for comprehensive reviews
- **Filtering**: Topic input can include keywords to narrow scope (e.g., "machine learning healthcare diagnosis" vs "machine learning healthcare")

## Example Queries

**Example 1 (All inputs provided):**
```
Topic: "Artificial Intelligence in Education"
Years: 2022-2026
Papers: 15
→ Returns table with top 15 papers on AI in education from 2022-2026
```

**Example 2 (Only topic provided):**
```
Topic: "Quantum Computing"
→ Returns table with top 25 papers on quantum computing from last 10 years
```

**Example 3 (Topic + year only):**
```
Topic: "Renewable Energy Storage"
Years: 2018-2024
→ Returns table with top 25 papers on renewable energy storage from 2018-2024
```

## Limitations
- Results dependent on Google Scholar's indexing
- Some papers may lack abstracts in search results
- Paywalled papers may not have full citation details visible

---

**Ready to use?** Provide:
1. Research topic (required)
2. Year range (optional - defaults to 10 years)
3. Number of papers (optional - defaults to 25)
4. Receive table with papers in your requested format
