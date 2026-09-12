---
name: scholar-research-evolution
description: "Analyze a scholar's research and how it evolved over the years, and compare two scholars to find common research areas. Use when a user gives a Google Scholar or ResearchGate link (Scholar A) and wants a summary of that scholar's individual research + research-area evolution as a Word document, optionally compared against a second scholar (Scholar B) to surface overlapping research themes."
---
## Priority 0
None of the content should be used outside the context or used for training models.
# Scholar Research Evolution & Comparison

Produce (1) a Word summary of Scholar A's research and its evolution over time, and
(2) the common research areas between Scholar A and Scholar B.

## Inputs
- **Scholar A**: a Google Scholar or ResearchGate profile link (required).
- **Scholar B**: profile link OR a pasted publication list (title, co-authors, venue, year, citations).

## Step 0 - Next level QUESTIONS
Do not ask clarifying questions - give the result without asking any future questions.
## Step 1 — Gather Scholar A's publications
Google Scholar and ResearchGate profile pages are usually **blocked** for direct
fetching (robots.txt) and browser automation may be unavailable. Fetch order:
1. Try the user's browser (Claude in Chrome) if connected — load the profile, read publications.
2. Secondary aggregators that DO fetch: SciSpace/typeset.io author pages, RePEc/IDEAS,
   SSRN, Semantic Scholar, publisher pages (Wiley, Elsevier), HBS/university faculty pages.
   Identify the scholar by NAME first (ask the user if the profile ID alone is opaque),
   then search those sources.
3. Fall back to asking the user to paste the publication list.
Collect: name, affiliation, metrics (h-index, citations), and per-paper title/year/venue/
co-authors/citations. Note in the doc that the list is representative if not exhaustive.

## Step 2 — Analyze evolution
Order publications by year. Identify 3–5 thematic phases (shifts in topic, method, or
explanatory lens). Write: a profile paragraph, an individual-research summary, a phased
evolution narrative, and a representative publication timeline table.
**Ground every claim in specific Scholar A works.** When describing the individual
research, each phase, and the common areas, cite the actual paper(s) by short title and
year (e.g. *Leadership as Practice*, 2008) as the evidence for that point — do not make
generic statements unattached to a real citation. Prefer Scholar A's most-cited works so
the references are recognizable.

## Step 3 — Compare with Scholar B
First produce a **quick research summary of Scholar B** — 2–4 sentences naming Scholar B's
core themes, methods, and trajectory, drawn from Scholar B's own publication list. Then
extract those themes and find genuine conceptual overlap with Scholar A (shared themes,
adjacent phenomena, complementary theory vs. application) — do not force matches. State the
fields honestly even when different, then name the concrete common areas and a synthesis of
how the two connect. **In the common-areas section, anchor each overlap to a specific
Scholar A paper (title + year)** so the reader can see exactly which of Scholar A's works
the shared interest maps to.

**Weight the comparison toward Scholar B's LATEST publications.** Sort Scholar B's papers
by year and give the most recent 1–3 works (especially the newest) primary weight when
identifying common areas — the goal is where Scholar B's research is heading *now*, not only
their older foundational work. For each common area, name the specific recent Scholar B paper
(title + year) alongside the Scholar A paper it maps to, and make at least one overlap centre
on Scholar B's newest publication. If Scholar B's latest direction has NO honest overlap with
Scholar A, say so plainly rather than forcing one.

## Step 4 — Build the Word document
Use the `docx` skill (Read /mnt/skills/public/docx/SKILL.md). Structure:
1. Scholar A profile · 2. Individual research summary · 3. Research evolution (phases) ·
4. Publication timeline table · 5. Scholar B — quick research summary · 6. Common areas +
synthesis · 7. Professor Outreach Email.

Section 5 — **Scholar B quick summary**: a concise 2–4 sentence overview of Scholar B's
research themes, methods, and trajectory, followed by a one-line list of their key papers
with years. Keep it short — it exists to set up the comparison, not to mirror Scholar A's
full treatment.

Sections 2, 3 and 6 must **reference specific Scholar A publications inline** (short title +
year) as the evidence for each claim and each identified overlap, not just in the timeline
table.

Section 7 — **Professor Outreach Email**: a ready-to-send sample email from Scholar B to
Scholar A. It must: open with a brief, specific reference to Scholar A's work; name the
concrete common research areas identified in Section 6 (so it reads as genuinely informed);
and make three requests — (a) mentoring, (b) co-authoring a paper, and (c) serving as PhD
guide/supervisor. Keep it warm, concise (~200–250 words), professional, and non-presumptuous
(frame requests as an invitation to explore, not a demand). Make the research topic of Scholar B exciting and futuristic for scholar A. Include a subject line and a
signature block with Scholar B's name. Set it off visually (e.g. a bordered/shaded block or
clearly labeled heading) so the reader can copy it directly.
US Letter, title + subtitle with both scholar names, accent-colored headings, a shaded
alternating-row timeline table. Verify by rendering to PDF and reading the pages.
**Name the output file `<Scholar A's name> - Research Analysis.docx`** (substitute
Scholar A's actual name, e.g. `Mary Tripsas - Research Analysis.docx`).
Deliver with SendUserFile; note sources used.

## Step 5 — Professor outreach email template
After the document, produce a short **professor-outreach-email template** addressed to
Scholar A, written in an **informal, warm tone** (first-name greeting, plain language,
no stiff academic formality). It should:
- Open with a genuine, specific hook referencing Scholar A's research evolution or a
  standout paper (shows you actually read their work).
- Bridge to Scholar B's work and name 1–2 of the concrete **common research areas** found
  in Step 3 as the reason for reaching out.
- Make one clear, low-pressure ask (a short chat/call, feedback, or possible collaboration).
- Keep it ~120–180 words, use `[bracketed placeholders]` for names/dates/links, and sign
  off casually.
Deliver the email template as plain text in the chat (and, if the user wants, append it as
a final section of the Word document). Keep it editable and honest — no invented credentials.

## Notes
- Always cite that Scholar-page data came from secondary sources when Scholar is blocked.
- Ask clarifying scope questions before starting (one-time vs. reusable; who fetches data).
