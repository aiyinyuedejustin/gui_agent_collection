# Hybrid Computer Use (HCU)

**Full title:** *Hybrid Computer Use: A Unified Programmatic, Semantic, and Visual Interface for General Agents*

- **Type:** Computer-use interface and agent harness integration
- **Paper:** https://arxiv.org/abs/2610.41432
- **Code:** https://github.com/microsoft/Hybrid-Computer-Use
- **Project:** https://microsoft.github.io/Hybrid-Computer-Use
- **Hugging Face paper:** https://huggingface.co/papers/2610.41432
- **Status:** Initial collection entry, based on the authors' announcement; quantitative results and implementation details await source-level review.

## Core idea

Provide a general-purpose agent with **three complementary computer-use channels**, allowing it to choose per action:

| Channel | Representation | Typical role |
| --- | --- | --- |
| **Code** | Programmatic interface, shell, scripts | Execute operations directly when exposed through code |
| **AX (Accessibility)** | Semantic accessibility tree and control properties | Read structured UI state and invoke accessibility actions |
| **GUI (Graphical User Interface)** | Screenshots, coordinates, mouse and keyboard | Visual fallback for controls that Code/AX cannot address |

AX is not merely a text substitute for a screenshot. It is an operating-system/application accessibility interface that can expose control roles, labels, values, and states; when supported, it may also be an **action** channel.

## Reported interface and performance features

- **Batched AX actions:** Group operations to reduce model/tool round trips.
- **Diff-based observations:** Return changed semantic state where possible instead of refreshing the entire observation after each action.
- **Hybrid selection:** The agent may switch among Code, AX, and GUI during one workflow.
- **Integration:** MCP server, CLI, and Python SDK support different agent harnesses and programmatic tool calling (PTC).
- **Benchmark claims:** The authors report improved efficiency and performance across OSWorld 2.0, OSWorld, WeaveBench, MacAgentBench, and Windows Agent Arena, including cross-model comparisons involving GPT, Claude, Gemini, and Grok. The announcement describes a state-of-the-art OSWorld 2.0 result; exact settings and comparability should be checked against the paper.

## Why it matters for agent infrastructure

1. **Action abstraction:** Decide where the boundary lies between model planning and deterministic programmatic execution.
2. **Observation economics:** Full screenshots versus accessibility snapshots versus state diffs have distinct latency, bandwidth, and token costs.
3. **Control fidelity:** Accessibility actions are structured and can be checked against semantic control state, but coverage varies by application.
4. **Harness portability:** MCP, CLI, and SDK surfaces let one environment interface connect to multiple agents.
5. **Evaluation fairness:** Step limits, tool budgets, observation cost, and allowed channels can change benchmark comparisons.

## Questions for deeper review

- What exact AX action operations are supported on each operating system and application type?
- How are AX selectors resolved, and how is stale UI state detected?
- How is observation diffing synchronized with asynchronous UI updates?
- Which actions require GUI fallback, and what does fallback cost?
- What is the security/permission model for Code, AX, and GUI?
- Are benchmark step budgets normalized across interfaces, and how is latency measured?
- How are tool calls, observations, retries, and trajectories recorded for reproducibility?

## Tags

`computer-use` · `gui-agent` · `hybrid-interface` · `accessibility` · `ax` · `harness` · `mcp` · `programmatic-tool-calling` · `benchmark`
