# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Purpose

This repository is a collection of academic papers (PDFs) transcribed into structured Markdown files stored in the `md/` folder. No build system, tests, or code exists — the work is purely document transcription.

## Research Context

The paper collection was assembled by a researcher investigating a single central question:

**Do women with a history of recurrent miscarriage (RM) — defined as ≥2 or ≥3 pregnancy losses depending on the study — experience a higher rate of placental complications in their subsequent pregnancies that do progress to viability?**

### The Hypothesis

Recurrent miscarriage and placental complications are proposed to lie on the same pathological continuum. A miscarriage represents one end of an underlying pathological process; a pregnancy that survives but develops placental complications represents the same underlying dysfunction without ending in loss. The two phenomena may share common mechanisms (e.g., defective trophoblast invasion, thrombophilia, immunological factors).

### Study Design Across Papers

Each paper takes a similar approach:
- **Exposure group**: Women with a history of RM (≥2 or ≥3 prior miscarriages)
- **Control group**: Women without a history of RM
- **Outcome**: Rate of adverse obstetric/perinatal events in *subsequent pregnancies* that progressed beyond early gestation

### Key Outcomes Tracked

Placental dysfunction disorders:
- Placental abruption
- Placenta previa
- Preeclampsia (preterm and term)
- Gestational hypertension

Perinatal outcomes:
- Preterm birth
- Low birth weight / small for gestational age (SGA)
- Intrauterine fetal death (stillbirth)
- Neonatal complications

## Markdown File Format

Each transcribed paper follows a consistent structure:

### 1. YAML Front Matter
```yaml
---
source: Journal Name
volume: 120
issue: "3, PT. 2"
pages: 626–634
doi: https://doi.org/10.xxxx/...
publisher: Publisher Name
received: Month DD, YYYY
revised: Month DD, YYYY
accepted: Month DD, YYYY
published: Month DD, YYYY
---
```
Hindawi papers also include `article_id` and `academic_editor`. Fields not present in the paper are omitted.

### 2. Header Block (after front matter)
- Article type as `# H1` (e.g., `# ORIGINAL ARTICLE: EARLY PREGNANCY` or `# Research Article`) — if present in the paper
- Paper title as `# H1`
- Authors as `**bold**` with `<sup>n</sup>` or `<sup>a</sup>` superscripts for affiliations
- Affiliations as a paragraph with `<sup>a</sup>` etc. labels
- Disclosure / funding / correspondence lines (verbatim from paper)
- Journal/copyright line
- Horizontal rule `---`

### 3. Abstract
- Hindawi style: `**Abstract**` heading, then plain paragraph
- Elsevier style: bold labels inline — `**Objective:**`, `**Design:**`, `**Setting:**`, etc.
- Followed by `*El resumen está disponible en Español al final del artículo.*` if present
- Key Words line
- Horizontal rule `---`

### 4. Body
- Top-level sections: `## SECTION NAME` (all-caps for Elsevier, title case for Hindawi)
- Subsections: `### 2.1. Subsection Name`
- Tables: standard markdown table syntax with `<sup>a</sup>` footnote markers in cells; footnotes listed directly below the table; caption as `*Author. Short title. Journal Year.*`
- Use `&nbsp;&nbsp;` for indented sub-rows (e.g., BMI subcategories, age groups)

### 5. References
- Numbered list, verbatim from paper

### 6. Spanish Abstract (Elsevier, if present)
- At the end of the file

## Critical Transcription Rules

- **Transcribe verbatim**, including apparent typos (e.g., `"congenital; malformation"`) and inconsistencies between text and tables
- Use `≥` and `≤` directly (not HTML entities)
- Use en-dash `–` for ranges (not hyphen)
- Superscript affiliation markers: `<sup>a</sup>` style for lettered, `<sup>1</sup>` style for numbered

## Reference Files

- `md/Jing Yang.md` — canonical example of Hindawi journal format
- `md/Jinwen Zhang.md` — canonical example of Elsevier (Fertility and Sterility) format with 4 tables and Spanish abstract
- `md/Eyal Sheiner.md` — example of a minimal older Elsevier paper (no YAML front matter, no article-type header)
- `md/Carlo Ticconi.md` — example of MDPI (J Clin Med) format, which differs from both Hindawi and Elsevier

## Global Rules

1. **Full-paper reading rule**: All paper reviews must read the complete paper — never rely on the abstract alone — unless the query explicitly specifies "abstract only."
2. **No prior knowledge rule**: Never infer or state anything based on external/prior knowledge. All outputs must be based exclusively on the content of the research materials stored in this project. This rule is absolute and cannot be waived.

## Workflow Notes

- Source PDFs are in the root directory alongside extracted text files (`.txt`, `.layout.txt`, `.raw.txt`, `.bbox.html`) used as transcription aids
- The `.tmp_mona_pages/` directory contains page images extracted from PDFs for visual reference
- When a PDF has complex layout (multi-column, tables), the `.layout.txt` file provides positional context and the `.bbox.html` provides bounding-box HTML for hard-to-parse sections
