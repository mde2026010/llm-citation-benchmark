# Citation Integrity Audit

## Submitted paper

**Benchmarking Citation Fabrication Rates Across Large Language Models and Agentic Search Tools**

The submitted paper contains **23 bibliography entries**. This audit independently checked the bibliographic identity of each entry against publisher, DOI, PubMed, ACL Anthology, arXiv, CourtListener, or another authoritative record.

## Result

| Status | Count | Rate |
|---|---:|---:|
| Valid | 22 | 95.65% |
| Partially valid / metadata error | 1 | 4.35% |
| Fabricated | 0 | 0.00% |
| **Total** | **23** | **100%** |

### Main finding

**No bibliography entry was classified as fully fabricated under the existence criterion. One reference (R22) was classified as partially valid because the DOI/title identify a real 2026 paper, but the authors named in the submitted paper are incorrect.**

The actual paper behind DOI `10.1007/s43465-026-01807-0` is by **İlhan Celil Özbek and Fatih Bağcıer**, not the authors stated in the submitted bibliography.

Therefore:

- **Fabrication rate (strict existence definition): 0 / 23 = 0.00%**
- **Material metadata-error rate: 1 / 23 = 4.35%**
- **Fully verified bibliography entries: 22 / 23 = 95.65%**

This is intentionally different from the paper's literature-review claims about model fabrication rates. The audit measures the **paper's own references**; the literature table measures **published studies' reported model error rates**.

## Important interpretation

A real citation with incorrect authors is not the same thing as a nonexistent citation. The audit therefore separates:

1. existence;
2. bibliographic accuracy;
3. source identity;
4. claim-level groundedness.

A citation can pass existence checking and still fail claim-level support.

## Reference-level audit

The machine-readable audit is available at:

`data/citation_audit_23_references.csv`

