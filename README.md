# GUI Agent Collection

持续收集和整理 **GUI Agent**、**Computer Use Agent（CUA）** 以及多模态 Agent 的论文、模型、Benchmark、环境和工程实现。

> 当前阶段：初步收录。优先保留原始资料和技术线索；论文精读、源码审查和实验复现将逐步补充。

## 已收录项目

| 项目 | 研究方向 | 原始资料 | 关键线索 |
| --- | --- | --- | --- |
| [WebHarbor](environments/webharbor.md) | Offline GUI Web Environment、Web Agent Benchmark、RL Environment | [论文](https://arxiv.org/abs/2611.03634) · [代码](https://github.com/aiming-lab/WebHarbor) · [环境与模型](https://huggingface.co/collections/ChilleD/webharbor) | 作者报告 153 个环境、3,518 个任务 |
| [Hybrid Computer Use (HCU)](frameworks/hybrid-computer-use.md) | Code / AX / GUI 混合交互接口、Agent Harness | [论文](https://arxiv.org/abs/2610.41432) · [代码](https://github.com/microsoft/Hybrid-Computer-Use) · [项目主页](https://microsoft.github.io/Hybrid-Computer-Use) | AX 动作执行、批量操作、差量观察 |

## 收录范围

- **基础能力**：GUI Grounding、视觉感知、Accessibility Tree（AX）、动作表示、规划、记忆与错误恢复。
- **交互范式**：Screenshot-and-Click、Browser Automation、AX、Code / DOM / GUI Hybrid Control、Mobile Agent、Desktop Agent。
- **模型与训练**：Vision-Language Model、Action Model、Synthetic Trajectory、Supervised Fine-Tuning、Reinforcement Learning、Online Adaptation。
- **Benchmark**：任务、Environment、Verifier、Metric、可复现性、数据污染和泛化能力。
- **基础设施**：Simulator、Virtual Machine、Container、Browser、Remote Desktop、Observation / Action API、调度、并发及 Tracing。
- **下游应用**：Web Workflow、Office Automation、Software Engineering、Mobile Apps、企业流程和跨设备交互。
- **学术生态**：Survey、开源 Framework、Dataset、Model Report、研究团队与产业系统。

## 仓库目录

| 目录 | 内容 |
| --- | --- |
| `surveys/` | 领域综述、分类体系、阅读路线 |
| `papers/` | 论文与技术报告 |
| `models/` | 模型、能力和训练方案 |
| `benchmarks/` | Benchmark 与评测基础设施 |
| `environments/` | Simulator、GUI Environment、Runtime |
| `frameworks/` | Agent Harness、交互工具与开源框架 |
| `applications/` | 下游应用场景 |
| `datasets/` | 训练/评测数据和 Trajectory 格式 |

仅在有实际资料时创建对应目录。

## 收录原则

1. 优先参考论文、官方文档、源码、Model Card 和 Benchmark Repository。
2. 记录发布日期、版本、原始链接、License 和维护状态。
3. 明确区分作者报告、独立验证结果与分析推断。
4. 允许一个项目属于多个研究方向，分类体系持续扩展。
5. 重点关注 2025 年以来的新工作，同时保留重要的奠基性研究。
6. 特别关注评测工程问题：环境部署、依赖、Rollout 控制、评分、成本、可复现性与失败模式。

## 条目模板

- **项目名称、类型、日期和版本**
- **原始资料**：Paper、Code、Documentation、Project Page
- **研究问题与核心贡献**
- **输入/输出模态与 Action Space**
- **Environment、依赖与部署架构**
- **训练或评测方法**
- **局限性、可复现性及常见问题**
- **相关研究与后续问题**

## License

仓库尚未选择 License；外部论文、代码与数据遵循各自的授权条款。
