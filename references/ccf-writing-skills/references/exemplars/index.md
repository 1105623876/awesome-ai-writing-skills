# Exemplar Index

Use this index when the user asks to learn writing moves from strong papers or explicitly chooses the source author's custom exemplar format. Load only the cards that match the target paper. Do not load every card by default.

## Optional Source-Author Format

Use `references/custom-format/default-user-format.md` only when the current user chooses that format. An unspecified venue does not activate it. The source author selected these two cards:

| Role | Venue | Card | Use when |
| --- | --- | --- | --- |
| Source-author exemplar | ICLR family | `cards/llava-4d.md` | 4D scene understanding, spatiotemporal prompts, dataset plus model papers |
| Source-author exemplar | CVPR | `cards/vggt.md` | feed-forward geometry, multi-task visual prediction, simple model versus optimization |

These two cards are sources for the optional exemplar format, not the current user's assumed preferences. Do not treat them as ordinary venue best-paper cards unless the user explicitly asks to compare against ICLR/CVPR best-paper style.

## Selection Rule

Pick at most 2-4 cards:

- Without a target venue, select by the current topic, evidence type, and requested style; do not default to the custom-format cards.
- Use same venue or venue family first when a target venue is specified.
- Use same evidence type second: theorem, benchmark, user study, system, dataset, or ablation-heavy model.
- Use same story shape third: new task, new benchmark, new model family, new capability, or new evaluation economy.
- Add one contrast card only when it improves reviewer-proofing.

Use cards to borrow writing moves, not claims, wordings, examples, or technical content.

## ICLR And CVPR Recent Best-Paper Cards

Use these cards when the user explicitly asks for ICLR/CVPR best-paper or outstanding-paper style.

| Venue/year | Card | Use when |
| --- | --- | --- |
| ICLR 2026 Outstanding Papers | `cards/iclr-2026-outstanding-papers.md` | theoretical succinctness or LLM conversation-failure papers |
| ICLR 2025 Outstanding Papers | `cards/iclr-2025-outstanding-papers.md` | safety alignment, fine-tuning dynamics, and uncertainty-guided exploration papers |
| ICLR 2024 Outstanding Papers | `cards/iclr-2024-outstanding-papers.md` | large-model reasoning, data curation, equivariance, and principled learning papers |
| CVPR 2025 Best Paper | `cards/cvpr-2025-vggt-best-paper.md` | CVPR best-paper status note for VGGT; load `cards/vggt.md` for writing moves |
| CVPR 2024 Best Papers | `cards/cvpr-2024-best-papers.md` | human-feedback text-to-image and generative image dynamics papers |
| CVPR 2023 Best Papers | `cards/cvpr-2023-best-papers.md` | visual programming and planning-oriented autonomous driving papers |

## Other Venue Cards

| Venue family | Card | Use when |
| --- | --- | --- |
| AAAI / theory and social choice | `cards/aaai-2025-every-bit-helps.md` | theorem-heavy papers that settle a parameterized open question |
| AAAI / biomedical generation | `cards/aaai-2024-gxvaes.md` | application-driven generative modeling with biological context and case studies |
| ICML / LLM agents | `cards/icml-2025-collabllm.md` | multiturn LLM collaboration, reward design, benchmark plus user study |
| ICML / video generation | `cards/icml-2024-videopoet.md` | multimodal autoregressive generation and zero-shot capability papers |
| ICCV / generative 3D vision | `cards/iccv-2025-brickgpt.md` | text-to-3D generation, physical constraints, dataset plus inference guardrails |
| ICCV / computational imaging | `cards/iccv-2023-passive-ultra-wideband.md` | passive sensing, extreme timescale imaging, hardware plus reconstruction |
| ECCV / computational imaging | `cards/eccv-2024-minimalist-vision.md` | hardware-software co-design, privacy/efficiency motivation, surprising minimalism |
| ECCV / representation analysis | `cards/eccv-2022-partial-distance-correlation.md` | statistical tools as versatile deep-learning regularizers or diagnostics |
| ACM MM / 3D affordance | `cards/acmmm-2025-aff3dfunc.md` | open-vocabulary 3D affordance understanding and robot validation |
| ACM MM / speech-video | `cards/acmmm-2024-speaker-to-dubber.md` | multimodal generation with alignment constraints and staged training |
| ACL / NLP benchmark | `cards/acl-2025-minilongbench.md` | benchmark compression, evaluation cost reduction, rank-correlation evidence |
| ACL / linguistic evaluation | `cards/acl-2024-mission-impossible.md` | cognitive/linguistic probes, synthetic tasks, claim-testing papers |
| NeurIPS / RL scaling | `cards/neurips-2025-1000-layer-ssl-rl.md` | scaling studies, capability emergence, self-supervised RL evidence |
| NeurIPS / image generation | `cards/neurips-2024-var.md` | new generation paradigm, scaling laws, next-scale prediction |

## Recommended Bundles

- Explicitly chosen source-author format: consult `references/custom-format/default-user-format.md` and the relevant `llava-4d.md` or `vggt.md` card.
- 4D embodied AI paper: `llava-4d.md`, `vggt.md`, `neurips-2025-1000-layer-ssl-rl.md`.
- ICLR-style theory or LLM paper: one ICLR recent best-paper card plus one same-topic card.
- CVPR-style vision paper: one CVPR recent best-paper card plus `vggt.md` if the paper involves 3D geometry or multi-task prediction.
- LLM collaboration or agent paper: `icml-2025-collabllm.md`, `acl-2025-minilongbench.md`.
- Generative multimodal system: `iccv-2025-brickgpt.md`, `acmmm-2024-speaker-to-dubber.md`, `icml-2024-videopoet.md`, `neurips-2024-var.md`.
- Data-efficient or cost-efficient evaluation: `acl-2025-minilongbench.md`, `aaai-2025-every-bit-helps.md`.
- Hardware or system paper: `eccv-2024-minimalist-vision.md`, `vggt.md`.
- Open-vocabulary robotics paper: `acmmm-2025-aff3dfunc.md`, `iccv-2025-brickgpt.md`.

## Output Reminder

For an exemplar-analysis request, the following can be useful. If the user only wants revised text, apply the relevant moves without adding a separate report:

1. Chosen exemplar set and why each card fits.
2. Transferable writing moves.
3. Drafting warnings where an exemplar's confidence would not be supported by the user's evidence.
4. A section plan or revision that is original to the user's paper.
