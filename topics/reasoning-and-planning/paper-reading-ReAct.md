# Paper Reading Note: ReAct: Synergizing Reasoning and Acting in Language Models

[Home](../../README.md) · [Paper Index](../../PAPER_INDEX.md)

## Metadata

- Paper ID: P004
- Verified title: ReAct: Synergizing Reasoning and Acting in Language Models
- Authors: Shunyu Yao; Jeffrey Zhao; Dian Yu; Nan Du; Izhak Shafran; Karthik Narasimhan; Yuan Cao
- Year / venue: 2022 preprint / ICLR 2023
- Primary source and version: [2210.03629v3](https://arxiv.org/html/2210.03629v3)
- Access date: 2026-11-20
- Reading status: reviewed
- Reproduction status: not attempted

## Problem and motivation

Couple planning and reasoning with observations so an agent can revise actions after new evidence (§1).

## Method and assumptions

ReAct augments the action space with language thoughts that update context without changing the environment. Frozen PaLM-540B uses manually authored few-shot trajectories. QA alternates thoughts and actions; decision tasks permit sparse thoughts. Wikipedia tools expose search, lookup, and finish (§2–3).

## Key ablations and comparison design

The central comparison separates reasoning-only (CoT), acting-only (Act), and combined reasoning/action (ReAct). Hybrid variants test whether internal knowledge and retrieval compensate for each other. Interpretation: isolate tool access from reasoning format before attributing a gain to reasoning itself. Source: §3.2–3.3.

## Claims and evidence

Experiments cover HotpotQA, FEVER, ALFWorld, and WebShop (§3–4; Tables 1–2), with Standard, CoT, Act, and hybrid baselines. The abstract reports absolute success improvements of 34 and 10 percentage points over trained baselines on ALFWorld and WebShop. ReAct is not uniformly better than CoT: unsuccessful retrieval can limit it (§3.3). [Primary paper](https://arxiv.org/html/2210.03629v3).

## Evaluation and reliability

Report task-specific correctness separately from interaction success. Match prompts, tool access, budgets, and model versions before comparing scores. Average success alone does not establish consistency across repeated runs.

## Mechanism and interpretation boundary

Interpretation: A language thought is part of a policy’s context, not a correctness certificate. Readability does not establish causal faithfulness, termination, or policy compliance.

## Critical assessment

Personal interpretation: The contribution is a feedback-driven control pattern. Prompt choice, retrieval quality, and inference budget can affect the measured gain. Human-editable thoughts offer an intervention interface but do not validate every generated explanation. Modern agents called ReAct may use substantially different scaffolds.

## Open questions and next experiment

Compare [τ-bench](../evaluation-and-reliability/paper-reading-τbench.md). Proposed experiment: compare Act and ReAct with matched model, examples, tool access, and budgets; separately ablate reasoning and external feedback.
