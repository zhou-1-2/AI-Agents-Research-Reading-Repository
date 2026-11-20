# Paper Reading Note: τ-Rec: A Verifiable Benchmark for Agentic Recommender Systems

[Home](../../README.md) · [Paper Index](../../PAPER_INDEX.md)

## Metadata

- Paper ID: P002
- Verified title: τ-Rec: A Verifiable Benchmark for Agentic Recommender Systems
- Authors: Bharath Sivaram Narasimhan; Karthik R. Narasimhan
- Year / venue: 2026 / ACM RecSys 2026 Resource Track
- Primary source and version: [2606.10156v1](https://arxiv.org/html/2606.10156v1)
- Access date: 2026-11-20
- Reading status: reviewed
- Reproduction status: not attempted

## Problem and motivation

Evaluate preference elicitation and constrained recommendation together, beyond static ranking and subjective model judging (§1).

## Method and assumptions

A partially observable tool–agent–user loop exposes catalog tools and a terminal recommendation tool. Reveal tags distinguish volunteered, on-request, and never-explicitly-revealed constraints. Typed catalog predicates and policy checks determine strict success (§3). The catalog uses TMDB movies; the simulator uses GPT-5 mini.

## Architecture and components

| Component | Role and interface |
| --- | --- |
| Movie catalog | Typed TMDB metadata supports constraint checks and catalog exploration. |
| Task specification | Encodes preferences, reveal tags, and active policies. |
| User simulator | Controls which preferences become available through dialogue. |
| Agent and tools | Agent asks questions, searches/filters/looks up catalog metadata, then submits through the recommendation tool. |
| Reward evaluator | Checks catalog predicates and policy compliance; strict success requires every required dimension. |
| Trial aggregator | Estimates pass^k across repeated episodes. |

Flow: initialize task and catalog → reveal preferences through dialogue and retrieve item evidence → submit candidate or handle infeasibility → score constraints/policies → aggregate trials. Source: paper §3.

## Task construction and coverage

Movie tasks combine catalog predicates, staged preference disclosure, and policy flags (§3–3.2). Catalog construction discovers recent TMDB releases, enriches metadata, and normalizes required fields. Coverage is constrained recommendation over structured movie metadata; it does not directly measure long-term satisfaction. Exact task counts and split details are not transcribed here and must be extracted from the pinned paper/data before replication.

## Claims and evidence

Abstract and §4 report nine configurations and best pass^1 around 57%, falling to about 35% at pass^4. The arXiv search abstract instead gives about 38%; use the explicitly linked v1 results here. The paper says five model families but lists six model names. These textual inconsistencies should remain visible. [Primary paper](https://arxiv.org/html/2606.10156v1).

## Evaluation and reliability

pass^k measures success on all k trials, unlike pass@k (at least one success). With c_t successes among n_t runs, estimate it by averaging C(c_t,k)/C(n_t,k) over tasks. Interpret repeated-run scores conditional on the simulator, task distribution, and configuration. Do not infer real-user reliability directly.

## Scoring validity and verification boundary

Interpretation: Executable predicates specify the benchmark, not subjective utility or a proof of agent correctness. Hidden constraints raise an identifiability issue: can the agent distinguish acceptable outcomes before terminal submission?

## Critical assessment

Personal interpretation: Hard constraints enable diagnosis but omit subjective taste, discovery, diversity, and long-term welfare. Fresh release dates alone do not prove freedom from contamination. The current code repository also contains a books extension; do not mix it into replication of the movie paper.

## Open questions and next experiment

Compare [τ-bench](../evaluation-and-reliability/paper-reading-τbench.md). 

Publication metadata: [DOI](https://doi.org/10.1145/3773078.3831847), RecSys 2026, pp. 915–919; [university publication record](https://collaborate.princeton.edu/en/publications/%CF%84-rec-a-verifiable-benchmark-for-agentic-recommender-systems/).

Proposed experiment: hold tasks and catalog fixed, vary reveal tags, and measure elicitation turns, strict success, policy violations, and pass^k. Separate infeasible tasks from failures to find feasible items.
