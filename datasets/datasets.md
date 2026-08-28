# Datasets and Benchmarks

The submitted paper identifies several benchmark families. The following resources are the most directly reusable for a future experimental extension of this project.

## ALCE
- **Purpose:** Automatic evaluation of long-form answers with citations.
- **Data:** ASQA, QAMPARI and ELI5.
- **Why useful:** Measures fluency, correctness and citation quality.
- **Source:** https://github.com/princeton-nlp/ALCE

## DeepResearch Bench
- **Purpose:** Evaluate deep-research agents on expert-designed research tasks.
- **Why useful:** Provides a controlled environment for future agentic-search comparisons.
- **Source:** https://github.com/Ayanami0730/deep_research_bench

## AuthorityBench
- **Purpose:** Study how citation presence and citation truth affect model epistemic behavior.
- **Why useful:** Separates claim truth from citation truth using a balanced factorial design.
- **Source:** https://github.com/floating-reeds/AuthorityBench

## LegalCiteBench
- **Purpose:** Evaluate legal citation retrieval, completion, error detection, matching, and verification.
- **Why useful:** Demonstrates how citation reliability can be measured as task-specific retrieval/verification rather than a single hallucination percentage.
- **Source:** https://arxiv.org/abs/2605.10186

## HalluLens
- **Purpose:** Dynamic hallucination benchmark with extrinsic and intrinsic tasks.
- **Why useful:** Useful model for avoiding benchmark leakage.
- **Source:** https://github.com/facebookresearch/HalluLens
