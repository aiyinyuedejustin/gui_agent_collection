# GUI Agent Collection

A curated, evolving knowledge base for **GUI Agents**, **Computer Use Agents (CUA)**, and multimodal agents that perceive and act in digital environments.

> Status: initialized. This repository is a collection framework; entries and findings will be added with primary-source references.

## Scope

- **Foundations** — GUI grounding, visual perception, accessibility trees (AX), action representations, planning, memory, and error recovery.
- **Interaction paradigms** — screenshot-and-click, browser automation, accessibility-based control, code/DOM/GUI hybrid control, mobile and desktop agents.
- **Models and training** — vision-language models, action models, synthetic trajectories, supervised fine-tuning, reinforcement learning, and online adaptation.
- **Benchmarks** — tasks, environments, evaluators, metrics, reproducibility, contamination, and generalization.
- **Infrastructure** — simulators, virtual machines, containers, browsers, remote desktops, observation/action APIs, orchestration, concurrency, and tracing.
- **Applications** — web workflows, office automation, software engineering, mobile apps, enterprise operations, and embodied or cross-device interfaces.
- **Surveys and ecosystems** — academic surveys, open-source frameworks, datasets, model reports, labs, and industry systems.

## Organization (planned)

| Directory | Content |
| --- | --- |
| `surveys/` | Field overviews, taxonomies, reading maps |
| `papers/` | Research papers and technical reports |
| `models/` | Model families, capabilities, training methods |
| `benchmarks/` | Benchmark cards and evaluation infrastructure |
| `environments/` | Simulators, GUI environments, runtime systems |
| `frameworks/` | Agent harnesses, tools, open-source implementations |
| `applications/` | Downstream tasks and deployment patterns |
| `datasets/` | Training/evaluation data and trajectory formats |

Directories will be created when they contain actual material.

## Collection principles

1. Prefer original papers, official documentation, source code, model cards, and benchmark repositories.
2. Record publication/update dates, versions, links, licenses, and maintenance status.
3. Separate confirmed source facts from analysis and speculation.
4. Classify entries across multiple dimensions; do not force every work into one category.
5. Emphasize recent work (especially 2025 onward) while retaining influential foundations.
6. Record practical evaluation-engineering details: environment setup, dependencies, rollout control, scoring, cost, reproducibility, and failure modes.

## Entry template

For each substantial item, capture:

- **Name / type / date / version**
- **Primary sources** (paper, code, docs, project page)
- **Problem and contribution**
- **Input/output modalities and action space**
- **Environment, dependencies, and deployment architecture**
- **Training or evaluation methodology**
- **Limitations, reproducibility, and known pitfalls**
- **Related work / open questions**

## License

No license has been selected yet. Content and external sources retain their respective rights.
