# Frontier model system cards & independent analysis

Last updated: 2026-10-12 (automated scheduled sweep).

Scope: real-frontier models from closed labs (Anthropic, OpenAI, Google) and open-weight labs (DeepSeek, Moonshot/Kimi, Z.ai/GLM), plus cyber-focused models where they appear. Small/cheap tiers (Haiku, Sonnet, Flash-Lite, etc.) are deliberately omitted, except Gemini 3.8 Flash, the newest Google card.

Analysis comes only from high-reputation evaluators: UK AISI (incl. joint UK AISI/CAISI work) and Irregular. Files under `analysis/` are text extractions of the source pages (figures and tables are on the source). The source URL is at the top of each file.

## Models

### Anthropic (`anthropic/`)
| Model | System card | Independent analysis |
|---|---|---|
| Claude Mythos Preview (Apr 2026) | [pdf](anthropic/claude-mythos-preview-system-card.pdf) | AISI: [cyber evaluation](analysis/aisi/our-evaluation-of-claude-mythos-previews-cyber-capabilities.md) |
| Claude Opus 4.7 | [pdf](anthropic/claude-opus-4-7-system-card.pdf) | none found |
| Claude Opus 4.8 | [pdf](anthropic/claude-opus-4-8-system-card.pdf) | none found |
| Claude Fable 5 / Mythos 5 | [pdf](anthropic/claude-fable-5-mythos-5-system-card.pdf) | none found |
| Claude Opus 5 | [pdf](anthropic/claude-opus-5-system-card.pdf) | Irregular: [Opus 5](analysis/irregular/assessing-claude-opus-5-against-offensive-security-benchmarks.md) (Jul 24) |
| Claude Fable 5.1 / Mythos 5.1 | [pdf](anthropic/claude-fable-5-1-mythos-5-1-system-card.pdf) | none found |
| Claude Opus 5.5 (Sep 2026) | [pdf](anthropic/claude-opus-5-5-system-card.pdf) | Irregular: [Opus 5.5](analysis/irregular/assessing-claude-opus-5.5-against-offensive-security-benchmarks.md) (Sep 22) |

### OpenAI (`openai/`)
Source: OpenAI Deployment Safety Hub (HTML, saved with a text extraction).
| Model | System card | Independent analysis |
|---|---|---|
| GPT-5.5 | not in repo (superseded; card not fetched) | AISI: [cyber evaluation](analysis/aisi/our-evaluation-of-openais-gpt-5-5-cyber-capabilities.md); Irregular: [GPT-5.5](analysis/irregular/assessing-gpt-5.5-against-offensive-security-benchmarks.md) |
| GPT-5.6 / 5.6 Sol | [txt](openai/gpt-5-6-system-card.txt) · [html](openai/gpt-5-6-system-card.html) | Irregular: [GPT-5.6 Sol](analysis/irregular/assessing-gpt-5.6-sol.md) |
| GPT-6 Astra (Sep 3, 2026; first OpenAI model rated "Critical" for cyber) | [txt](openai/gpt-6-astra-system-card.txt) · [html](openai/gpt-6-astra-system-card.html) | AISI: [unsanctioned supply-chain attacks in simulations](analysis/aisi/gpt-6-astra-performs-unsanctioned-supply-chain-attacks-in-simulations.md); Irregular: [GPT-6 Astra](analysis/irregular/assessing-gpt-6-astra.md) |
| GPT-6.1 Sol (addendum) | [txt](openai/gpt-6-1-sol-system-card.txt) · [html](openai/gpt-6-1-sol-system-card.html) | none found |
| GPT-6 Sol / Luna, Oct 2026 update | [txt](openai/gpt-6-october-system-card.txt) · [html](openai/gpt-6-october-system-card.html) | none found |

### Google DeepMind (`google/`)
| Model | Model card | Independent analysis |
|---|---|---|
| Gemini 3 Pro (Nov 2025) | [pdf](google/Gemini-3-Pro-Model-Card.pdf) · [FSF report](google/fsf-gemini-3-pro.html) | see cross-model incident reports below |
| Gemini 3.1 Pro (Feb 2026) | [pdf](google/Gemini-3-1-Pro-Model-Card.pdf) | none found |
| Gemini 3.8 Flash (Sep 2026) | [pdf](google/Gemini-3-8-Flash-Model-Card.pdf) | none found |

### Open weights (`open-weights/`)
| Model | Report | Independent analysis |
|---|---|---|
| DeepSeek-V4 (Pro / Flash) | [tech report (arXiv 2606.19348)](open-weights/deepseek/deepseek-v4-technical-report-2606.19348.pdf) | none found |
| Kimi K3 (Jul 2026) | [tech report (arXiv 2607.24653)](open-weights/kimi/kimi-k3-technical-report-2607.24653.pdf) | AISI/CAISI: [preliminary cyber assessment](analysis/aisi/preliminary-assessment-of-kimi-k3s-cyber-capabilities.md); Irregular: [Kimi K3](analysis/irregular/assessing-kimi-k3-against-offensive-security-benchmarks.md) |
| GLM-5 (Z.ai) | [tech report (arXiv 2602.15763)](open-weights/glm/glm-5-technical-report-2602.15763.pdf) | Irregular: [GLM-5.2](analysis/irregular/assessing-glm-5.2-against-offensive-security-benchmarks.md) |

## Cross-model analysis
UK AISI (`analysis/aisi/`):
- [Cheating behaviour in frontier model evaluations](analysis/aisi/cheating-behaviour-in-frontier-model-evaluations.md) (Jul 21)
- [Incident report: unsanctioned agent behaviour during cyber testing](analysis/aisi/incident-report-unsanctioned-agent-behaviour-during-cyber-testing.md) (Aug 4)
- [How far behind the frontier are open-weight models on cyber](analysis/aisi/how-far-behind-the-frontier-are-leading-open-weight-models-on-cyber.md) (Jul 17)
- [How fast is autonomous AI cyber capability advancing](analysis/aisi/how-fast-is-autonomous-ai-cyber-capability-advancing.md) (May 13)
- [Frontier AI agents on multi-step cyber-attack scenarios](analysis/aisi/how-do-frontier-ai-agents-perform-in-multi-step-cyber-attack-scenarios.md) (Mar 16)
- [Inference scaling in cyber tasks](analysis/aisi/evidence-for-inference-scaling-in-ai-cyber-tasks-increased-evaluation-budgets-reveal-higher-success-rates.md) (Mar 5)
- [Harnessing frontier AI for cyber defence](analysis/aisi/harnessing-frontier-ai-for-cyber-defence.md) (Mar 31)
- [Frontier AI Trends Report: 5 key findings](analysis/aisi/5-key-findings-from-our-first-frontier-ai-trends-report.md)

Irregular (`analysis/irregular/`):
- [Containment challenges: testing the boundaries of cyber evaluations](analysis/irregular/containment-challenges-testing-the-boundaries-of-cyber-evaluations.md) (Oct 5)
- [FrontierCyber benchmark](analysis/irregular/frontiercyber.md) (Jun 22)
- [Emerging evidence of a capability shift](analysis/irregular/emerging-evidence-of-a-capability-shift.md)
- [Cyber capabilities exceed standard evaluation budgets](analysis/irregular/cyber-capabilities-exceed-standard-evaluation-budgets.md) (Mar 5)
- Other labs' models, for context: [Meta Muse Spark 1.1](analysis/irregular/assessing-muse-spark-1.1-against-offensive-security-benchmarks.md)

## Known gaps / watchlist
- **Gemini 4 Argon** (announced Sep 30, gated to cyber defenders via Google's Fairwind program): no model card published yet per press coverage. Check deepmind.google/models/model-cards.
- **OpenAI GPT-5.6-Cyber** (Aug 2026, restricted access): no system card found on the Deployment Safety Hub.
- **Mistral Large 4**: weights, tech report and model card promised by end of Oct 2026 (secondary reports).
- **Meta Muse Spark 1.1**: closed model with a safety report, not fetched (ai.meta.com not retrieved). Irregular analysis included above.
- **Open-weight Hugging Face model cards** (Kimi-K3, GLM-5.2/5.3, DeepSeek-V4.1-Flash, V4-Pro-0813) and DeepSeek's own transparency-center PDFs are not saved: the sandbox proxy blocks deepseek.com, huggingface.co and github.com. GLM-5.2/5.3 and DeepSeek V4.1 have no tech report in the repo.
- Older cards (Opus 4.6 and earlier, Gemini 2.5, GPT-5 and earlier) intentionally not included.
- Possible AISI/Irregular pages for Fable 5.x/Mythos 5.x were not found in their listings as of this run.
