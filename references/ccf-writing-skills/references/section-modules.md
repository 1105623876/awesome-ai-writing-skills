# Technical Paper Sections

> Adapted for ai-writing on 2026-10-07 from [CCFA section-modules.md](https://github.com/mikubaka88/CCFA-Skills/blob/5969e6b20a3bbcef9118fa00796d1417d48fcbf3/ccf-paper-writer/references/section-modules.md), with citation examples from [research-writing-patterns.md](https://github.com/mikubaka88/CCFA-Skills/blob/5969e6b20a3bbcef9118fa00796d1417d48fcbf3/ccf-paper-writer/references/research-writing-patterns.md). MIT [LICENSE](../LICENSE).
> Selected the Introduction, Related Work, Method, Experiments, and Figures/Tables sections. Removed family calls, citation and length quotas, the NeurIPS drafting fallback, fixed table formatting, and unsupported causal shortcuts; retained section questions, citation guidance, and examples.

Read only the relevant section. Local polishing preserves the existing organization, notation, citations, and claim strength. Use structural suggestions when drafting, restructuring, or diagnosing an unclear passage. Questions below are aids, not required reports. Missing results or evidence remain missing; substantive claim changes follow the user's authorization.

The numbered organizations below list content roles, not required headings. Give a part its own subsection only when it answers a distinct reader question and needs more than a paragraph or two; otherwise merge it with its neighbor. Keep sections required by the venue template.

## Introduction For Method Papers

Use this when the contribution is a method, model, or system and the target is a computer-science venue, or the manuscript already follows this convention. A finding-led or question-driven paper can use [nature-introduction.md](../../nature-writing/references/nature-introduction.md) instead. Neither is a required paragraph count.

Paragraph roles often used in such introductions:

1. Task, application, or scientific value.
2. What existing methods achieve, as a progression rather than a flat list.
3. The remaining gap and the technical reason it persists.
4. The idea that addresses that reason, and a short preview of the method.
5. Contributions, each mapped to the experiment, proof, or analysis that supports it.

Write only the roles the material supports. A gap needs a technical or empirical reason, not "nobody has tried this"; when the material gives no such reason, flag it instead of inventing one. Do not frame the contribution as a patch over a naive baseline, and do not inflate an ordinary improvement into a field-level insight.

Citation rules:

- Every claim about what prior work does needs a citation. A paragraph that describes "existing methods" without any is incomplete.
- Cover the foundations, closest approaches, and the gap with verified citations. Citation count is not a completeness criterion.
- Put the claim first and the citation second, so the sentence still reads without the brackets: "Large-scale pretraining on web-scale data [4,5] has become the dominant paradigm..." rather than "Brown et al. [4] and Chowdhery et al. [5] proposed..."
- Prefer the concept as sentence subject ("Self-attention mechanisms [1]...") over a run of "Author et al. [N] proposed" sentences.

Checks:

- Does the core challenge appear early enough?
- Is the reason for the gap explicit?
- Do cited prior methods explain the actual gap and the closest alternatives?
- Does each contribution map to Method and Experiments?
- Does the reader understand the mechanism-level difference and what it enables?

## Related Work

Goal: make the difference from prior work easy to verify.

Possible structure for each topic group:

1. The research thread and why it is relevant here.
2. Representative methods grouped by a shared observation, not listed one by one: "Contrastive objectives [9,10,11] share the goal of learning invariant representations, but differ in how negative pairs are constructed."
3. What the group as a whole leaves unresolved for this paper's problem.
4. The technical distinction of this paper, in technical terms: "In contrast, our method removes the need for paired data by..." rather than "Unlike previous work, our method is superior."

Citation rules:

- Each group needs the works that support its argument; a narrow topic may need only one decisive source. Do not fill a fixed citation quota.
- Support every factual claim about a research thread with specific citations, not vague references to "prior work".
- Cite a paper because it serves the point being made, not because it is famous.
- Discuss the closest competitor explicitly in its own sentence or paragraph. Do not bury it in a citation list.
- Do not invent citations. If the closest work is unknown and retrieval is within scope, search for it; otherwise name the missing comparison.

Checks:

- Are the strongest and most recent competitors included?
- Is the distinction technical rather than promotional?
- Does Related Work prepare the reader for the Method?

## Method

Goal: make the mechanism auditable and reproducible.

Questions to use when the method is hard to follow; answer from the supplied material, without inventing modules:

1. What modules exist?
2. For each module, what is the workflow?
3. Why is the module needed?
4. Why should it work?
5. What assumptions, hyperparameters, or implementation details matter?

Possible organization; use only the parts appropriate to the contribution:

1. Overview: setting, core idea, pipeline figure, section map.
2. Component descriptions: purpose, operation, and the reason for the design. A theory, resource, or protocol paper need not be recast as a model with modules.
3. Implementation details: reproducible specifics.
4. Complexity, assumptions, or proof sketch when relevant.

Citation rules:

- Any borrowed component, architecture, or technique must cite its original source. Do not describe a well-known module as if it were original.
- Cite borrowed modules, the base architecture, and adapted objectives or optimization methods where relevant; use evidence coverage rather than a citation quota.
- When a module builds on or replaces prior work, cite that work and explain the actual difference. Do not invent an antecedent or novelty claim.

Style rule:

- Do not use bold inline labels (`\textbf{Input:}`, `\textbf{Output:}`, `\textbf{Architecture:}`) in every paragraph. Write prose that flows: "The encoder takes a sequence of tokens and produces contextualized representations through stacked self-attention layers" rather than "`\textbf{Encoder:}` The encoder uses self-attention."
- Do not let theorem statements, equations, or notation blocks replace explanation. Introduce their purpose before the formalism and explain their role afterward.
- Avoid `Q1`/`C1`-style labels for modules or claims unless the venue or task convention requires them.

Checks:

- Can a reviewer reconstruct the pipeline from text and figure?
- Is each component's purpose and operation clear, without claiming an advantage that has not been established?
- Are inputs, outputs, notation, and symbols defined before use?
- Which design claims are supported by ablation, theorem, analysis, or user study, and which remain assumptions?
- Are citations present for borrowed components? Verify missing sources when retrieval is within scope; otherwise identify the missing citation without inventing it.

## Experiments

Goal: test the central scientific claims and explain the observations.

Possible organization; use only the parts appropriate to the contribution:

1. Setup: datasets, metrics, baselines, protocol, implementation.
2. Main comparison: answer whether the method works.
3. Ablation: test the role of components and design choices; an ablation alone need not identify a unique mechanism.
4. Analysis: answer when it works, when it fails, and how robust it is.
5. Qualitative or case studies when the venue expects them.
6. Material observed limitations or failure cases at the relevant location, or in a required dedicated section.

Citation rules:

- Cite the datasets, nontrivial metrics, and baselines actually used. Do not add irrelevant citations to reach a quota.
- When comparing against prior published results, cite both the method paper and the source of the specific numbers being compared.
- Distinguish measured comparisons from literature descriptions. A cited method may be discussed without reported comparison results, but must not be presented as an evaluated baseline.

Checks:

- Does each empirical claim have corresponding evidence? A proof or documented resource may support a different kind of contribution.
- Use the supplied experiment settings and results. If the user requests study design, separate proposed tests from completed experiments; do not invoke another skill automatically.
- Are baselines strong, recent, and fair? Is every baseline cited?
- Are metrics standard and sufficient?
- Are ablations tied to modules and design choices?
- Does each table and figure have a clear evidential purpose?
- Are negative or boundary results reported where they change interpretation, without repeating caveats elsewhere?

## Figures And Tables

Goal: make the paper inspectable before close reading.

Structural rules:

1. Give each figure or table a clear evidential purpose; related panels may answer several connected questions.
2. Captions explain what is shown, conditions, units, and how to read the display. Placement follows the actual venue template.
3. Follow the existing table style and venue requirements; do not add packages just to enforce a preferred appearance.
4. Use consistent precision for comparable quantities, preserving meaningful uncertainty and the accuracy of reported values.
5. If results are highlighted, use a consistent convention and do not imply statistical significance from ranking alone.
6. For narrow columns, use clear abbreviations or natural line wrapping while keeping units and labels understandable.
7. Fit wide tables to the actual page layout without making text unreadable or deleting necessary comparisons.
8. Pipeline figures should show data flow, modules, and outputs without overcrowding.
9. Qualitative figures should avoid cherry-picking by showing representative successes and failures when possible.

Checks:

- Can the paper's contribution be understood from figures and captions?
- Are key claims visible in tables or figures?
- Are visual examples aligned with the text discussion?
- Are values, units, uncertainty, labels, and highlighting consistent with the text and the supplied results?
