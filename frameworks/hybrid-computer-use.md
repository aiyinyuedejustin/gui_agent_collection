# Hybrid Computer Use（HCU）

论文全称：*Hybrid Computer Use: A Unified Programmatic, Semantic, and Visual Interface for General Agents*

- **类型**：Computer Use Interface、Agent Harness 集成
- **论文**：https://arxiv.org/abs/2610.41432
- **代码**：https://github.com/microsoft/Hybrid-Computer-Use
- **项目主页**：https://microsoft.github.io/Hybrid-Computer-Use
- **Hugging Face Paper**：https://huggingface.co/papers/2610.41432
- **研究深度**：D0，依据作者介绍初步收录，后续再分析源码及实验细节。

## 核心思路

为通用 Agent 提供 **Code、AX、GUI 三种互补的 Computer Use 通道**，由 Agent 在执行每一步时选择合适的接口。

| 通道 | 信息表示 | 典型用途 |
| --- | --- | --- |
| **Code** | Shell、Script、Programmatic API | 能直接通过代码完成的操作 |
| **AX（Accessibility）** | Accessibility Tree、控件角色和状态 | 读取结构化 UI 状态，执行语义层控件操作 |
| **GUI（Graphical User Interface）** | Screenshot、坐标、鼠标和键盘 | 处理 Code / AX 无法覆盖的界面操作 |

AX 不仅是 Screenshot 的文本替代品。操作系统或应用的 Accessibility 接口可以暴露控件的 Role、Label、Value 和 State；在支持的情况下，还能直接执行 Action。因此 AX 同时可以是 **Observation Channel** 和 **Action Channel**。

## 作者介绍的机制与结果

- **Batched AX Actions**：将多个 AX 操作合并执行，减少模型与工具之间的往返。
- **Diff-based Observation**：尽可能只返回改变的语义状态，避免每一步都获取完整 Observation。
- **Hybrid Selection**：同一 Workflow 中动态切换 Code、AX 和 GUI。
- **多种接入方式**：MCP Server、CLI、Python SDK，可对接不同 Agent Harness 和 Programmatic Tool Calling（PTC）。
- **Benchmark**：作者报告在 OSWorld 2.0、OSWorld、WeaveBench、MacAgentBench、Windows Agent Arena 上提升了效率和性能，并展示 GPT、Claude、Gemini、Grok 等模型的跨模型结果。作者宣称在 OSWorld 2.0 达到 SOTA，具体实验设置与可比性待阅读论文后分析。

## 对 Agent 基础设施的意义

1. **Action Abstraction**：模型规划和确定性程序执行如何分工？
2. **Observation Cost**：完整 Screenshot、AX Snapshot 与 State Diff 的延迟、带宽、Token 成本不同。
3. **Control Fidelity**：AX 动作具有结构化语义，也可以依据控件状态校验，但不同软件的覆盖率存在差异。
4. **Harness Portability**：MCP、CLI、SDK 使环境操作接口能够服务多种 Agent。
5. **Evaluation Fairness**：Step Limit、Tool Budget、Observation Cost、可用通道都会影响 Benchmark 的可比性。

## 后续重点研究问题

1. 不同操作系统和应用支持哪些 AX Action？
2. AX Selector 如何定位控件？界面变化后如何处理 Stale State？
3. Observation Diff 怎样与异步 UI 更新同步？
4. 哪些操作需要回退到 GUI？Fallback 的开销有多大？
5. Code、AX、GUI 各自的权限及安全边界是什么？
6. Benchmark 如何统一 Step Budget？Latency 怎样统计？
7. Tool Call、Observation、Retry 和 Trajectory 如何记录，才能复现实验？

## 标签

`computer-use` · `gui-agent` · `hybrid-interface` · `accessibility` · `ax` · `harness` · `mcp` · `programmatic-tool-calling` · `benchmark`
