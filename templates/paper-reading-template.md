# Paper Reading Note: [Title]

[Home](../../README.md) · [Paper Index](../../PAPER_INDEX.md)

## Metadata

- Paper ID:
- Verified title / authors / year:
- Paper type: benchmark / method / system / theory
- Venue or preprint status:
- Primary source / DOI:
- Version and access date:
- Reading status: queued
- Reproduction status: not attempted

## Problem and motivation

State the research question, prior limitation, evaluation unit, and principal contribution.

## Method and assumptions

Explain the central design and assumptions. For method papers, describe inputs, outputs, training/inference, and what differs from the closest baseline.

## Architecture and components

Benchmark papers only; omit for other paper types unless necessary. Describe the end-to-end execution flow and component boundaries.

| Component | Role / inputs / outputs | Agent-visible or evaluator-only state |
| --- | --- | --- |

Cover task specification, dataset/environment, tested agent, tools, simulator if present, evaluator, and trial aggregation. Identify resets, termination, and sources of randomness. Cite sections.

## Task construction and coverage

Benchmark papers only. Record task provenance, scale, splits, difficulty, annotation/QA, feasible and infeasible cases, release version, and coverage gaps. Distinguish missing details from details not yet checked.

## Evaluation protocol and reliability

Record baselines, models/scaffolds, metrics and exact success criterion, budgets, repeated runs, uncertainty, costs, and contamination controls. Separate partial progress from strict success and pass^k from pass@k. For method papers, include ablations that isolate the proposed mechanism.

## Main results and evidence

| Claim | Evidence location | Setting and reported result | Qualification |
| --- | --- | --- | --- |

Include negative results and failure modes. Distinguish reported results from reproduced observations.

## Validity and limitations

Examine scoring errors, simulator validity, representativeness, confounds, leakage, and alternative valid solutions. Explain what the checker or proof actually guarantees. Include formal analysis only when it adds a concrete specification or meaningful guarantee boundary.

## Critical assessment

State the strongest contribution, the weakest supported inference, and your interpretation. Avoid repeating the results or generic praise.

## Open questions and next experiment

Link related notes and propose a concrete comparison with controls, metrics, and a falsifiable outcome.

<!-- Add a Reproduction record only after an actual attempt: exact versions, configuration, commands, seeds, artifacts, and observed results. Until then, use the metadata status. Adjust navigation links to the note's final depth. -->
