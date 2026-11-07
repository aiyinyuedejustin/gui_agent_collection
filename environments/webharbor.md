# WebHarbor

- **类型**：Offline GUI Web Environment、Web Agent Benchmark、Reinforcement Learning（RL）训练环境
- **发布时间**：2026 年 11 月
- **论文**：https://arxiv.org/abs/2611.03634
- **代码**：https://github.com/aiming-lab/WebHarbor
- **环境与模型**：https://huggingface.co/collections/ChilleD/webharbor
- **Hugging Face Paper**：https://huggingface.co/papers/2611.03634
- **研究深度**：D0，依据作者发布介绍初步收录，后续再进行论文与源码审查。

## 解决什么问题

1. **Web Agent Benchmark 失真**：真实网站持续变化，CAPTCHA 干扰测试，且登录后的深层 Workflow 很难稳定评测。作者介绍中提到 WebVoyager 有 22% 的任务过时，Online-Mind2Web 则频繁遇到 reCAPTCHA。
2. **缺少可重复使用的 RL 环境**：通过复制真实网站形成 Offline Environment，提供可执行任务与独立 Verifier，使涉及登录的复杂 Workflow 能够反复运行并用于 RL。

## 发布规模与实验结果

| 指标 | 作者报告 |
| --- | --- |
| 贡献者 | 26 所学校和机构的 57 人 |
| Offline Web Environment | 153 个 |
| Task | 3,518 个 |
| Environment Reset | 单环境 Sub-second |
| 训练模型 | webharbor-4B |
| Online-Mind2Web 成绩 | 70.4 |

“开源规模最大、质量最高”以及“超越同规模开源 GUI Agent”属于作者发布时的比较性主张，后续需要结合评测协议和同期工作分析。

## 对评测基础设施的意义

- **Environment Fidelity**：Clone 真实网站，让测试覆盖状态变化和业务操作，而不仅是静态截图与公开页面。
- **State Lifecycle**：快速 Reset 能降低大规模并行 Rollout 和 RL 采样的环境开销。
- **Task Verification**：每个 Task 配备 Verifier，有利于按最终状态自动评分，而非只比较点击轨迹。
- **Authentication Workflow**：登录后操作更接近 Personal Agent 的真实使用范围。
- **Multimodal Assets**：包含大量图片的网页可检验视觉 Grounding 与多模态理解能力。

## 后续重点研究问题

1. 网站如何 Clone、打包、初始化和分发？资源授权如何处理？
2. Reset 恢复了哪些状态？高并发情况下是否保持确定性？
3. Verifier 如何设计？成功条件、隐藏状态和 Trust Boundary 是什么？
4. 登录账号、Session、用户数据与任务状态如何模拟？
5. Train/Test 如何隔离？怎样控制数据泄漏与网站模板重叠？
6. Browser、Container 和运行环境如何编排？扩容瓶颈在哪里？
7. Online-Mind2Web 70.4 的具体测试协议是什么？

## 标签

`gui-agent` · `web-agent` · `offline-environment` · `benchmark` · `reinforcement-learning` · `verifier` · `web-simulation` · `multimodal`
