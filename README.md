# Frontier model system cards & independent analysis

Last updated: 2026-11-28 (automated scheduled sweep).

Scope: real-frontier models from closed labs (Anthropic, OpenAI, Google) and open-weight labs (DeepSeek, Moonshot/Kimi, Z.ai/GLM), plus cyber-focused models where they appear. Small/cheap tiers (Haiku, Sonnet, Flash-Lite, etc.) are deliberately omitted, except Gemini 3.8 Flash and Gemini 4 Hydrogen (kept because its safety report has a full cyber-capability chapter and it hits Google's cyber CCL alert threshold).

Analysis comes only from high-reputation evaluators: UK AISI (incl. joint UK AISI/CAISI work) and Irregular. Files under `analysis/` are text extractions of the source pages (figures and tables are on the source). The source URL is at the top of each file.

## Models

### Anthropic (`anthropic/`)
| Model | System card | Independent analysis |
|---|---|---|
| Claude Mythos Preview (Apr 2026) | [pdf](anthropic/claude-mythos-preview-system-card.pdf) | AISI: [cyber evaluation](analysis/aisi/our-evaluation-of-claude-mythos-previews-cyber-capabilities.md) |
| Claude Opus 4.7 | [pdf](anthropic/claude-opus-4-7-system-card.pdf) | none found |
| Claude Opus 4.8 | [pdf](anthropic/claude-opus-4-8-system-card.pdf) | none found |
| Claude Fable 5 / Mythos 5 | [pdf](anthropic/claude-fable-5-mythos-5-system-card.pdf) | none found |
| Claude Opus 5 | [pdf](anthropic/claude-opus-5-system-card.pdf) | Irregular: [Opus 5](analysis/irregular/assessing-claude-opus-5-against-offensive-security-benchmarks.md) (Jul 24); [monitoring as feedback / tripwire bypass](analysis/irregular/monitoring-as-feedback-how-ai-agents-learn-to-work-around-controls.md) (Nov 26) |
| Claude Fable 5.1 / Mythos 5.1 | [pdf](anthropic/claude-fable-5-1-mythos-5-1-system-card.pdf) | none found |
| Claude Opus 5.5 (Sep 2026) | [pdf](anthropic/claude-opus-5-5-system-card.pdf) | Irregular: [Opus 5.5](analysis/irregular/assessing-claude-opus-5.5-against-offensive-security-benchmarks.md) (Sep 22) |
| Claude Fable 5.2 / Mythos 5.2 (Nov 9, 2026; Anthropic's strongest cyber model to date, still "lower" FCF cyber tier) | [pdf](anthropic/claude-fable-5-2-mythos-5-2-system-card.pdf) | none yet. AISI: [alignment failures in AISI's incident](analysis/aisi/investigating-alignment-failures-in-aisis-incident.md) covers Mythos 5 |

### OpenAI (`openai/`)
Source: OpenAI Deployment Safety Hub (HTML, saved with a text extraction).
| Model | System card | Independent analysis |
|---|---|---|
| GPT-5.5 | not in repo (superseded; card not fetched) | AISI: [cyber evaluation](analysis/aisi/our-evaluation-of-openais-gpt-5-5-cyber-capabilities.md); Irregular: [GPT-5.5](analysis/irregular/assessing-gpt-5.5-against-offensive-security-benchmarks.md) |
| GPT-5.6 / 5.6 Sol | [txt](openai/gpt-5-6-system-card.txt) · [html](openai/gpt-5-6-system-card.html) | Irregular: [GPT-5.6 Sol](analysis/irregular/assessing-gpt-5.6-sol.md) |
| GPT-6 Astra (Sep 3, 2026; first OpenAI model rated "Critical" for cyber) | [txt](openai/gpt-6-astra-system-card.txt) · [html](openai/gpt-6-astra-system-card.html) | AISI: [unsanctioned supply-chain attacks in simulations](analysis/aisi/gpt-6-astra-performs-unsanctioned-supply-chain-attacks-in-simulations.md); Irregular: [GPT-6 Astra](analysis/irregular/assessing-gpt-6-astra.md) |
| GPT-6.1 Sol (addendum) | [txt](openai/gpt-6-1-sol-system-card.txt) · [html](openai/gpt-6-1-sol-system-card.html) | none found |
| GPT-6.1 Terra (Oct 26, 2026; addendum) | [txt](openai/gpt-6-1-terra-system-card.txt) · [html](openai/gpt-6-1-terra-system-card.html) | none found |
| GPT-6 Cyber (Nov 5, 2026; cyber-focused) | [txt](openai/gpt-6-cyber-system-card.txt) · [html](openai/gpt-6-cyber-system-card.html) | Irregular: [GPT-6 Cyber](analysis/irregular/assessing-gpt-6-cyber-against-offensive-security-benchmarks.md) (Nov 5) |
| **GPT-6.2 Astra / GPT-6.2 Sol (Nov 17, 2026; OpenAI's most capable deployed model; both Critical for cyber, High bio; Astra first released model at High AI self-improvement)** | [pdf](openai/gpt-6-2-astra-sol-system-card.pdf) · [txt](openai/gpt-6-2-astra-sol-system-card.txt) · [html](openai/gpt-6-2-astra-sol-system-card.html) | Irregular: [GPT-6.2 Astra](analysis/irregular/assessing-gpt-6.2-astra-against-offensive-security-benchmarks.md) (Nov 17). The card also includes UK AISI external evaluations of cyber safeguards, alignment and monitorability |
| **GPT-6.2 in ChatGPT (Nov 23, 2026; chat-tab variant of GPT-6.2 for Plus/Pro; Critical cyber, High bio, High AI self-improvement; same safeguards as 6.2 Astra/Sol)** | [pdf](openai/gpt-6-2-chatgpt-system-card.pdf) · [txt](openai/gpt-6-2-chatgpt-system-card.txt) · [html](openai/gpt-6-2-chatgpt-system-card.html) | none yet |
| GPT-6 Sol / Luna, Oct 2026 update | [txt](openai/gpt-6-october-system-card.txt) · [html](openai/gpt-6-october-system-card.html) | Irregular: [monitoring as feedback / tripwire bypass (GPT-6 Sol)](analysis/irregular/monitoring-as-feedback-how-ai-agents-learn-to-work-around-controls.md) (Nov 26) |

### Google DeepMind (`google/`)
| Model | Model card | Independent analysis |
|---|---|---|
| Gemini 3 Pro (Nov 2025) | [pdf](google/Gemini-3-Pro-Model-Card.pdf) · [FSF report](google/fsf-gemini-3-pro.html) | see cross-model incident reports below |
| Gemini 3.1 Pro (Feb 2026) | [pdf](google/Gemini-3-1-Pro-Model-Card.pdf) | none found |
| Gemini 4 Argon (Oct 13, 2026; FSF: cannot rule out cyber CCL) | [pdf](google/Gemini-4-Argon-Model-Card.pdf) · [safety & security report](google/gemini-4-argon-safety-security-report.pdf) · [web card](google/gemini-4-argon-model-card-page.html) | Irregular: [Gemini 4 Argon](analysis/irregular/assessing-gemini-4-argon-against-offensive-security-benchmarks.md) (Oct 13) |
| Gemini 4 Carbon (Nov 10, 2026; general-release model built on Argon; cyber CCL not ruled out, mitigations deployed) | [pdf](google/Gemini-4-Carbon-Model-Card.pdf) · [safety & security report](google/gemini-4-carbon-safety-security-report.pdf) | none yet |
| Gemini 4 Neon (Nov 18, 2026; mid tier between Carbon and Hydrogen, adapted from Carbon; cyber CCL "cannot be ruled out", carried forward from Argon) | [pdf](google/Gemini-4-Neon-Model-Card.pdf) · [safety & security report](google/gemini-4-neon-safety-security-report.pdf) (Nov 2026) | none yet |
| Gemini 4 Hydrogen (Nov 12, 2026; fast tier adapted from Carbon; cyber CCL not reached but alert threshold reached) | [pdf](google/Gemini-4-Hydrogen-Model-Card.pdf) · [safety & security report](google/gemini-4-hydrogen-safety-security-report.pdf) | none yet |
| Gemini 3.8 Flash (Sep 2026) | [pdf](google/Gemini-3-8-Flash-Model-Card.pdf) | none found |

### Open weights (`open-weights/`)
| Model | Report | Independent analysis |
|---|---|---|
| DeepSeek-V4 (Pro / Flash) | [tech report (arXiv 2606.19348)](open-weights/deepseek/deepseek-v4-technical-report-2606.19348.pdf) | none found |
| Kimi K3.1 Pro (Nov 2026; 2.8T params, open weights) | [HF model card](open-weights/kimi/kimi-k3.1-pro-model-card.md) (no tech report yet) | Irregular: [monitoring as feedback / tripwire bypass](analysis/irregular/monitoring-as-feedback-how-ai-agents-learn-to-work-around-controls.md) (Nov 26) |
| Kimi K3 (Jul 2026) | [tech report (arXiv 2607.24653)](open-weights/kimi/kimi-k3-technical-report-2607.24653.pdf) | AISI/CAISI: [preliminary cyber assessment](analysis/aisi/preliminary-assessment-of-kimi-k3s-cyber-capabilities.md); Irregular: [Kimi K3](analysis/irregular/assessing-kimi-k3-against-offensive-security-benchmarks.md) |
| GLM-5 / 5.2 / 5.3 (Z.ai; 5.3 Oct 2026, "emergent cyber capability", SOTA open-weight CyberGym) | [tech report (arXiv 2602.15763)](open-weights/glm/glm-5-technical-report-2602.15763.pdf) · [GLM-5.3 HF model card](open-weights/glm/glm-5.3-model-card.md) | Irregular: [GLM-5.2](analysis/irregular/assessing-glm-5.2-against-offensive-security-benchmarks.md); [GLM-5.3](analysis/irregular/glm-5.3-multi-stage-cyber-operations-and-instruction-violations.md) (Oct 28); [monitoring as feedback](analysis/irregular/monitoring-as-feedback-how-ai-agents-learn-to-work-around-controls.md) (Nov 26) |
| Reflection Beam (Oct 2026; first open-weight model, Safety Technical Report not saved) | not in repo | Irregular: [Beam](analysis/irregular/assessing-reflection-beam-against-offensive-security-benchmarks.md) (Oct 16) |

## Cross-model analysis
UK AISI (`analysis/aisi/`):
- [Attack policy selection can make monitor evaluations misleading](analysis/aisi/attack-policy-selection-can-make-monitor-evaluations-misleading.md) (Nov 23; case study on an ex-production OpenAI GPT-5.4 monitor)
- [Cheating behaviour in frontier model evaluations](analysis/aisi/cheating-behaviour-in-frontier-model-evaluations.md) (Jul 21)
- [Incident report: unsanctioned agent behaviour during cyber testing](analysis/aisi/incident-report-unsanctioned-agent-behaviour-during-cyber-testing.md) (Aug 4)
- [How far behind the frontier are open-weight models on cyber](analysis/aisi/how-far-behind-the-frontier-are-leading-open-weight-models-on-cyber.md) (Jul 17)
- [How fast is autonomous AI cyber capability advancing](analysis/aisi/how-fast-is-autonomous-ai-cyber-capability-advancing.md) (May 13)
- [Frontier AI agents on multi-step cyber-attack scenarios](analysis/aisi/how-do-frontier-ai-agents-perform-in-multi-step-cyber-attack-scenarios.md) (Mar 16)
- [Inference scaling in cyber tasks](analysis/aisi/evidence-for-inference-scaling-in-ai-cyber-tasks-increased-evaluation-budgets-reveal-higher-success-rates.md) (Mar 5)
- [Investigating alignment failures in AISI's incident (Mythos 5)](analysis/aisi/investigating-alignment-failures-in-aisis-incident.md) (Oct 23)
- [Building a more secure environment for evaluating dangerous capabilities](analysis/aisi/building-a-more-secure-environment-for-evaluating-dangerous-capabilities.md) (Oct 1)
- [Finding cloud misconfigurations with frontier AI: case study](analysis/aisi/finding-cloud-misconfigurations-with-frontier-ai-a-case-study.md) (Jul 7)
- [Can AI agents escape their sandboxes? Container-breakout benchmark](analysis/aisi/can-ai-agents-escape-their-sandboxes-a-benchmark-for-safely-measuring-container-breakout-capabilities.md)
- [Harnessing frontier AI for cyber defence](analysis/aisi/harnessing-frontier-ai-for-cyber-defence.md) (Mar 31)
- [Frontier AI Trends Report: 5 key findings](analysis/aisi/5-key-findings-from-our-first-frontier-ai-trends-report.md)

Irregular (`analysis/irregular/`):
- [Monitoring as feedback: how AI agents learn to work around controls](analysis/irregular/monitoring-as-feedback-how-ai-agents-learn-to-work-around-controls.md) (Nov 26; GPT-6 Sol, Claude Opus 5, GLM-5.3, Kimi K3.1 bypass tripwire controls)
- [Containment challenges: testing the boundaries of cyber evaluations](analysis/irregular/containment-challenges-testing-the-boundaries-of-cyber-evaluations.md) (Oct 5)
- [Addressing recent incidents: ongoing findings and path forward](analysis/irregular/addressing-recent-incidents-ongoing-findings-and-path-forward.md)
- [Emergent offensive cyber behaviour in AI agents](analysis/irregular/emergent-offensive-cyber-behavior-in-ai-agents.md)
- [Offense at scale: how frontier AI lowers the cost of cyber attacks](analysis/irregular/offense-at-scale-how-frontier-ai-lowers-the-cost-of-cyber-attacks.md)
- [Agentic self-modification in open-weights systems](analysis/irregular/agentic-self-modification-in-open-weights-systems.md) (Sep 16)
- [FrontierCyber benchmark](analysis/irregular/frontiercyber.md) (Jun 22)
- [Emerging evidence of a capability shift](analysis/irregular/emerging-evidence-of-a-capability-shift.md)
- [Cyber capabilities exceed standard evaluation budgets](analysis/irregular/cyber-capabilities-exceed-standard-evaluation-budgets.md) (Mar 5)
- Other labs' models, for context: [Meta Muse Spark 1.1](analysis/irregular/assessing-muse-spark-1.1-against-offensive-security-benchmarks.md)

## Known gaps / watchlist
- **Gemini 3.8 Flash Cyber**: referenced in Irregular's Argon analysis; no standalone model card found on the DeepMind model-cards page.
- **OpenAI GPT-5.6-Cyber** (Aug 2026, restricted access): no system card found on the Deployment Safety Hub.
- **Mistral Large 4**: weights, tech report and model card promised by end of Oct 2026 (secondary reports).
- **Meta Muse Spark 1.1**: closed model with a safety report, not fetched (ai.meta.com not retrieved). Irregular analysis included above.
- **Open-weight model cards**: Kimi K3.1 Pro and GLM-5.3 cards now saved via the Hugging Face Hub connector. DeepSeek's transparency-center PDFs remain unreachable (deepseek.com blocked). DeepSeek V4.1-Flash / V4.1-Flash-1017 (Nov 10) are Flash-tier and omitted; no new DeepSeek Pro-tier release or tech report found.
- **Independent analysis pending** for Claude Fable 5.2 / Mythos 5.2, Gemini 4 Carbon / Neon / Hydrogen, GPT-6.2 Sol / GPT-6.2 in ChatGPT: no dedicated AISI or Irregular assessment as of 2026-11-28.
- **Alibaba Qwen4-Max** (Nov 16, per secondary reporting): out of the current lab scope; no system card found.
- **Open-weight labs**: no new DeepSeek, Kimi or GLM frontier release or tech report since 2026-11-14 (checked HF Hub and HF Papers on 2026-11-28). No Kimi K3.1 tech report yet.
- OpenAI GPT-6 Luna Oct 29 addendum, CSAM image classifier card (Nov 16), GPT-Rosalind-6 (bio), GPT-Live-1.1 and ChatGPT Images 2.6 cards omitted as non-frontier/non-cyber.
- Older cards (Opus 4.6 and earlier, Gemini 2.5, GPT-5 and earlier) intentionally not included.
- Anthropic Haiku 5.5 / Sonnet 5.5 cards (Sep-Oct 2026) deliberately omitted as non-frontier tiers; Fable 5.2 / Mythos 5.2 added Nov 2026.
- Possible AISI/Irregular pages for Fable 5.x/Mythos 5.x were not found in their listings as of this run.
