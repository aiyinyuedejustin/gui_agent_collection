# WebHarbor

- **Type:** Offline GUI web environments; Web Agent benchmark and reinforcement-learning environment collection
- **Published:** November 2026
- **Paper:** https://arxiv.org/abs/2611.03634
- **Code:** https://github.com/aiming-lab/WebHarbor
- **Environments and model:** https://huggingface.co/collections/ChilleD/webharbor
- **Hugging Face paper:** https://huggingface.co/papers/2611.03634
- **Status:** Initial collection entry, based on authors' release announcement; implementation and numerical claims await source-level review.

## What it addresses

1. **Benchmark drift and access limitations:** Public websites change, CAPTCHA interrupts evaluation, and workflows behind login are difficult to assess consistently. The announcement cites 22% outdated tasks in WebVoyager and recurring reCAPTCHA in Online-Mind2Web.
2. **Training environments for Web Agents:** Offline replicas of actual websites with executable tasks and associated verifiers enable repeatable, login-dependent workflows and reinforcement learning (RL).

## Reported release and results

| Item | Authors' reported figure |
| --- | --- |
| Contributors | 57 from 26 schools and organizations |
| Offline web environments | 153 |
| Tasks | 3,518 |
| Reset time | Sub-second per environment |
| Example trained model | webharbor-4B |
| Online-Mind2Web score | 70.4 |

The statements about being the largest or highest-quality open-source set and outperforming comparable-size agents are **author claims**, not independent rankings.

## Why it matters for evaluation infrastructure

- **Environment fidelity:** Cloned websites allow evaluation beyond static screenshots and simple public-page browsing.
- **State lifecycle:** Fast reset changes the throughput economics of parallel rollouts and RL.
- **Task verification:** Per-task verifiers support automated outcome scoring rather than relying only on action similarity.
- **Authentication workflows:** Login-dependent tasks test deeper application state and personal-agent-like interaction.
- **Multimodal assets:** Image-rich websites exercise visual grounding in realistic interfaces.

## Questions for deeper review

- How are original sites cloned, packaged, initialized, and legally redistributed?
- What state does reset restore, and is it truly deterministic under concurrency?
- What is each verifier's trust boundary, and what constitutes success?
- How are credentials, sessions, user data, and hidden task states modeled?
- How is train/test separation handled, and how are leakage and site-template overlap measured?
- What are runtime requirements, container or browser orchestration details, and scalability limits?
- Which evaluation protocol produces the reported 70.4 score?

## Tags

`gui-agent` · `web-agent` · `offline-environment` · `benchmark` · `reinforcement-learning` · `verifier` · `web-simulation` · `multimodal`
