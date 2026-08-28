# Citation Integrity Audit

## Purpose

This document describes the verification protocol for the AI-assisted research paper associated with this repository.

The course activity requires researchers to verify references rather than accepting AI-generated citations blindly. The supplied instruction sheet explicitly says that the title, authors, publication year, journal/conference, DOI where available, existence of the paper, and correspondence of the supplied link should be checked.

## Historical paper profile

The earlier activity recorded:

- Approximate pages: **11**
- Approximate word count: **~4,900 including references / ~4,200 body**
- Main sections: **7**
- Total references: **23**
- Approximate in-text citation occurrences: **~54**
- AI warning to verify references independently: **No**

These values describe the earlier paper and are retained as an activity record. They are not themselves a reference-verification result.

## Verification categories

### VALID

Use when:

- the work exists;
- the title is substantially correct;
- the authors correspond;
- the year is consistent;
- the venue is consistent;
- DOI/identifier, when supplied, resolves to the same work;
- the link points to the same work.

### PARTIALLY_VALID

Use when the work exists but one or more meaningful bibliographic fields are wrong, such as:

- incorrect year;
- incorrect venue;
- incomplete or incorrect author list;
- incorrect DOI;
- title drift that still permits confident identification.

### FABRICATED

Use when the claimed scholarly work cannot be verified as an existing work after the defined search procedure, or when the citation combines incompatible metadata from different works.

## Recommended audit table

| ID | Generated citation | Exists? | Title | Authors | Year | Venue | DOI | Link | Status | Verification source | Notes |
|---|---|---|---|---|---|---|---|---|---|---|---|
| R1 | Add generated reference | | | | | | | | | | |
| R2 | Add generated reference | | | | | | | | | | |
| ... | ... | | | | | | | | | | |
| R23 | Add generated reference | | | | | | | | | | |

## Calculation

Let:

- `N` = total references checked
- `F` = fabricated references
- `P` = partially valid references
- `V` = valid references

Then:

```text
Fabrication rate = F / N × 100
Partial-error rate = P / N × 100
Validity rate = V / N × 100
```

Always report the denominator.

## Important distinction

A fabricated bibliographic reference is not identical to a broken URL. A genuine paper can have a stale or broken web link, and a fabricated URL may not correspond to a fabricated bibliographic record. Agentic-search evaluations therefore benefit from separately measuring:

1. bibliographic identity;
2. URL resolution;
3. source identity;
4. citation-to-claim support.

## Evidence sources

Prefer:

- publisher pages;
- DOI/Crossref;
- OpenAlex;
- Semantic Scholar;
- PubMed when relevant;
- official conference proceedings;
- official arXiv records for preprints.

Do not classify a reference as genuine merely because a search engine returns a similar title.

## Reproducibility record

For each verification session, record:

- date;
- verifier;
- search source;
- exact query where useful;
- final metadata;
- decision;
- reason for ambiguous decisions.

This makes the audit independently inspectable.
