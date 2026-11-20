# Paper Reading Note: OSWorld2.0: Benchmarking Computer Use Agents on Long-Horizon Real-World Tasks

[Home](../../README.md) · [Paper Index](../../PAPER_INDEX.md)

## Metadata

- Paper ID: P003
- Verified title: OSWorld2.0: Benchmarking Computer Use Agents on Long-Horizon Real-World Tasks
- Authors: Mengqi Yuan; Zilong Zhou; Xinzhuang Xiong; et al. (full list in source)
- Year / venue: 2026 / arXiv preprint
- Primary source and version: [2606.29537v1](https://arxiv.org/html/2606.29537v1)
- Access date: 2026-11-20
- Reading status: reviewed
- Reproduction status: not attempted

## Problem and motivation

Evaluate complete professional and everyday computer workflows rather than isolated UI actions. There are 108 tasks; median human duration is about 1.6 hours (Abstract; §2).

## Method and assumptions

Task-specific files, desktop applications, self-hosted services, bounded-knowledge user simulation, and dynamic updates create controlled stateful workflows. Construction includes human proposal, implementation, peer review, and evaluator auditing (§2.1).

## Architecture and components

| Component | Role and interface |
| --- | --- |
| Task and initial snapshot | Instructions, files, accounts, prior records, and application state define a coherent workflow. |
| Desktop and self-hosted services | Provide stateful application surfaces and controllable web environments. |
| Agent scaffold | Connects the tested model to observation/action tools and execution budgets. |
| User simulation | Answers clarification questions from bounded task-specific knowledge where configured. |
| Dynamic update hooks | Inject new task information during execution where configured. |
| Evaluators | Functional and model-based checks score final outcomes and partial progress; safety is audited separately. |

Flow: restore initial environment → execute and observe across applications, including clarification/updates → evaluate artifacts and final state → report completion, partial progress, and safety. Source: paper §2.1 and §3.1.

## Task construction and coverage

The 108 workflows are constructed primarily through internally trained annotators, with supporting interviews, questionnaires, and synthetic proposals (§2.1). Peer review checks feasibility and ambiguity; implementation adds environment snapshots and evaluators. Task length, profession, and challenge phenomena describe coverage (§2.2). Professional-domain subgroup sizes and evaluator validation should be checked before making subgroup claims.

## Claims and evidence

At 500 steps, the abstract reports best binary completion of 20.6% and partial score of 54.8%. Evaluation uses functional and model-based checks (§2.1.3); safety is analyzed separately (§4.2). Qualitative failures include missing constraints, stale interface observations, and inadequate verification (§4.4). [Primary paper](https://arxiv.org/html/2606.29537v1).

## Evaluation and reliability

Report task-specific correctness separately from interaction success. Match prompts, tool access, budgets, and model versions before comparing scores. Average success alone does not establish consistency across repeated runs.

## Scoring validity and verification boundary

Interpretation: Final-state checks do not prove temporal compliance. Proposed specifications include monitoring updates, asking for missing evidence, and verifying outputs before submission. Model-based grading adds evaluator uncertainty.

## Critical assessment

Personal interpretation: Realistic artifacts improve ecological validity while increasing scoring complexity. Audit alternative valid outputs and adversarial near-misses. Horizon is confounded with professional knowledge and application difficulty. Tool batching changes the meaning of a step, so compare calls and tokens as well as step limits.

## Open questions and next experiment

Compare [τ-bench](../evaluation-and-reliability/paper-reading-τbench.md). 

Proposed experiment: add a persistent constraint ledger and final verification phase at matched action/token budgets. Measure whether gains reflect complete workflows rather than only partial credit.
