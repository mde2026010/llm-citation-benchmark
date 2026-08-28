# Awesome Citation Fabrication Benchmark

A curated research repository on **benchmarking citation fabrication rates across Large Language Models (LLMs) and agentic search/deep-research tools**.

The repository connects an AI-assisted research-paper activity with citation-integrity auditing and a reusable collection of verified scholarly literature, datasets/benchmarks, tools, implementations, and learning resources.

> **Core principle:** AI can help discover candidate references, but every scholarly resource should be independently verified before it is treated as evidence.

## Contents

- [Overview](#overview)
- [Research Questions](#research-questions)
- [AI-Assisted Research Paper](#ai-assisted-research-paper)
- [Citation Integrity Audit](#citation-integrity-audit)
- [Verified Research Papers](#verified-research-papers)
- [Datasets and Benchmarks](#datasets-and-benchmarks)
- [Tools and Libraries](#tools-and-libraries)
- [GitHub Implementations](#github-implementations)
- [Tutorials and Learning Resources](#tutorials-and-learning-resources)
- [Verification Method](#verification-method)
- [Suggested Experimental Protocol](#suggested-experimental-protocol)
- [Limitations](#limitations)
- [License](#license)

## Overview

Large language models can produce fluent, persuasive answers while still generating unsupported facts or unreliable references. Citation fabrication is a particularly auditable form of this problem because a reference can be checked against scholarly metadata services and publisher records. Earlier empirical work has reported substantial fabrication and citation-error rates in some LLM-generated bibliographies, while newer work has expanded the question to citation URLs and deep-research agents.

This project focuses on **citation integrity rather than general text quality**. The main unit of analysis is a reference or citation supplied by an LLM or an agentic research system. A useful evaluation should distinguish at least three outcomes:

1. **Valid** — the cited work exists and the bibliographic identity is substantially correct.
2. **Partially valid / inaccurate** — the cited work exists, but one or more important bibliographic fields are wrong.
3. **Fabricated / hallucinated** — the claimed scholarly work cannot be verified as an existing work under the defined verification protocol.

For agentic systems, the project also distinguishes **citation URL validity** from **bibliographic reference validity**. A URL can fail because it is fabricated, non-resolving, or simply stale, so these failure modes should not automatically be treated as the same phenomenon.

## Research Questions

- How often do LLMs generate fabricated scholarly references?
- How does fabrication vary by model, prompt, discipline, and reference format?
- Do newer models consistently reduce citation fabrication?
- How do ordinary LLMs compare with web-search and deep-research agents?
- What is the difference between a fabricated bibliographic reference and a fabricated/non-resolving citation URL?
- Which verification methods are most reproducible and scalable?

## AI-Assisted Research Paper

**Topic:** Benchmarking Citation Fabrication Rates Across Large Language Models and Agentic Search Tools.

The repository is designed to hold the student's own earlier AI-assisted paper without redistributing copyrighted third-party papers.

- `paper/README.md` — paper placement and metadata
- Add your own paper PDF as `paper/AI_Assisted_Research_Paper.pdf`

## Citation Integrity Audit

The earlier course activity reported the following paper-level audit profile:

| Measure | Reported value |
|---|---:|
| Approximate pages | 11 |
| Approximate word count | ~4,900 including references / ~4,200 body |
| Main sections | 7 |
| Total references | 23 |
| Approximate in-text citation occurrences | ~54 |
| AI warning to independently verify references | No |

The repository does **not** treat those historical summary numbers as proof that every one of the 23 earlier references was genuine. The audit procedure in `citation-audit/Citation_Integrity_Audit.md` defines how each reference should be checked.

## Verified Research Papers

The repository contains **20 verified scholarly papers/resources** selected for relevance to citation fabrication, citation accuracy, hallucination detection, citation generation, and deep-research evaluation.

See:

- `references/references.md`
- `data/paper_catalog.csv`

Categories:

- Citation fabrication and accuracy
- Citation recommendation and citation generation
- Hallucination detection/evaluation
- Citation-supported generation
- Agentic/deep-research evaluation

## Datasets and Benchmarks

See `datasets/datasets.md`.

Included resources include:

- ALCE
- DeepResearch Bench
- DRBench
- BrowseComp
- HaluEval
- HalluLens
- HALoGEN

## Tools and Libraries

See `tools/tools.md`.

The workflow emphasizes:

- Crossref
- OpenAlex
- Semantic Scholar
- DOI resolution
- PubMed where applicable
- Unpaywall
- RAGAS / citation-evaluation tooling

## GitHub Implementations

See `implementations/github-repositories.md`.

The collection prioritizes projects with research connections, documentation, reproducibility, and active/public source code.

## Tutorials and Learning Resources

See `tutorials/tutorials.md` for authoritative documentation and benchmark pages useful for reproducing the verification workflow.

## Verification Method

For every candidate scholarly reference:

1. Normalize the title, authors, year, venue, and DOI.
2. Search an authoritative metadata source.
3. Confirm that the record exists.
4. Compare the generated and verified title.
5. Compare author identity.
6. Compare publication year.
7. Compare venue/publisher.
8. Compare DOI when available.
9. Check whether the supplied link points to the same work.
10. Assign a final status: `valid`, `partially_valid`, or `fabricated`.
11. Record the verification source and date.

For URL-based citations from research agents, additionally record:

- HTTP/URL resolution status
- whether the destination is the claimed source
- whether the URL appears to be a genuine but stale link
- whether an archival record exists when needed

## Suggested Experimental Protocol

A reproducible benchmark can use the same prompt set across systems.

### Phase 1 — Generate

For each model/agent:

- use identical research prompts;
- request a fixed number of scholarly references;
- save the raw output;
- record model name/version, date, prompt, and tool mode.

### Phase 2 — Parse

Extract each reference into structured fields:

`title | authors | year | venue | DOI | URL`

### Phase 3 — Verify

Run the reference through multiple metadata sources and manually resolve ambiguous cases.

### Phase 4 — Score

At minimum calculate:

- **Fabrication rate** = fabricated references / total references
- **Partial-error rate** = partially valid references / total references
- **Validity rate** = valid references / total references
- **URL non-resolution rate** for agentic citation links

### Phase 5 — Compare

Compare systems using the same:

- prompts
- number of trials
- citation budget
- verification rules
- exclusion criteria

Do not compare percentages obtained from studies with incompatible definitions as if they were directly equivalent.

## Limitations

- Citation fabrication definitions differ across studies.
- A reference can exist but still be bibliographically inaccurate.
- A URL can be broken because of link rot rather than fabrication.
- Search-engine indexing is not a perfect proof of non-existence.
- Different disciplines have different DOI and metadata conventions.
- Model versions and product configurations change over time.
- Results from published studies should not be presented as if they were measurements made in this repository.

## Reproducibility Checklist

- [ ] Record exact model/version.
- [ ] Record exact prompt.
- [ ] Record date/time of generation.
- [ ] Save raw outputs.
- [ ] Save parsed references.
- [ ] Save verification results.
- [ ] Use consistent classification rules.
- [ ] Report denominators, not only percentages.
- [ ] Keep an audit trail for ambiguous cases.
- [ ] Do not upload copyrighted third-party PDFs without permission.

## Repository Structure

```text
awesome-citation-fabrication-benchmark/
├── README.md
├── paper/
│   └── README.md
├── citation-audit/
│   └── Citation_Integrity_Audit.md
├── references/
│   └── references.md
├── datasets/
│   └── datasets.md
├── tools/
│   └── tools.md
├── implementations/
│   └── github-repositories.md
├── tutorials/
│   └── tutorials.md
├── data/
│   └── paper_catalog.csv
└── LICENSE
```
