# Research Map

[Home](README.md)

## Organizing perspective

Study agents through their control loop: observe, retrieve, reason, plan, act, evaluate, and update. This is an organizing lens rather than a claim that all systems share one architecture.

- [Agent Foundations](topics/agent-foundations/README.md): Agent definitions, architectures, autonomy, control loops, and workflow design.
- [Reasoning and Planning](topics/reasoning-and-planning/README.md): Task decomposition, search, reflection, decision making, and long-horizon planning.
- [Tool Use and Environment Interaction](topics/tool-use-and-environment-interaction/README.md): Tool selection, API execution, browser interaction, feedback, and environment modeling.
- [Memory and Knowledge](topics/memory-and-knowledge/README.md): Working and persistent memory, retrieval, knowledge representation, and memory maintenance.
- [Multi-Agent Systems](topics/multi-agent-systems/README.md): Coordination, communication, delegation, shared state, and collective decision making.
- [Agent Training and Learning](topics/agent-training-and-learning/README.md): Supervised learning, reinforcement learning, feedback, adaptation, and experience reuse.
- [Agent Evaluation & Reliability](topics/evaluation-and-reliability/README.md): Task and trajectory evaluation, robustness, reproducibility, failure analysis, calibration, and recovery.
- [Formal Methods for Agents](topics/formal-methods-and-verification/README.md): Specifications, contracts, invariants, model checking, runtime monitoring, and assurance boundaries.
- [Safety and Security](topics/safety-and-security/README.md): Threat models, prompt injection, authorization, privacy, misuse, and defensive evaluation.
- [Systems and Infrastructure](topics/systems-and-infrastructure/README.md): Orchestration, observability, execution isolation, state persistence, latency, and cost.
- [Applications and Domains](topics/applications-and-domains/README.md): Agentic Recommender Systems, software engineering, research assistants, and domain-specific workflows.

## Priority research threads

| Thread | Questions to investigate | Evidence to seek |
| --- | --- | --- |
| Agent Evaluation & Reliability | How do failures accumulate over trajectories? How stable are results across runs? | Explicit success criteria, repeated trials, uncertainty, failure taxonomy, recovery costs |
| Formal Methods for Agents | Which actions and state transitions admit useful specifications? | Stated assumptions, formal properties, monitor coverage, counterexamples |
| Agentic Recommender Systems | How do interactive recommendation actions affect user goals over time? | Preference fidelity, constraint satisfaction, exposure effects, longitudinal evaluation |

## Suggested reading progression

Start with foundations, then evaluation and reliability, then formal methods. Connect planning, tools, memory, learning, and infrastructure to these priorities. Use applications to formulate concrete evaluation settings.

No literature coverage or research maturity is implied by this map.
