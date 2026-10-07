# Main-Text Discipline for Scientific Papers

> Adapted for ai-writing on 2026-10-07 from [upstream](https://github.com/Yuan1z0825/nature-skills/blob/7d5f160ebfe8033375b4afef7c5911aa4203c983/skills/nature-shared/core/main-text-discipline.md).
> Modified scope, task boundaries, fixed structures, and mandatory audits; retained detailed guidance and examples. License: [Apache-2.0](../LICENSE).

Use this reference when drafting, restructuring, compressing, or revising
the main text of a scientific manuscript, especially Results. It operationalizes
an author-supplied writing discipline; it is not a journal policy. Current
journal instructions and field-specific reporting standards override it when
they require information in the main text.

## Contents

- [1. Separate evidence completeness from main-text completeness](#1-separate-evidence-completeness-from-main-text-completeness)
- [2. Classify every result before placement](#2-classify-every-result-before-placement)
- [3. Build the shortest sufficient evidence chain](#3-build-the-shortest-sufficient-evidence-chain)
- [4. Prevent revision accretion](#4-prevent-revision-accretion)
- [5. Separate main text, captions, and SI](#5-separate-main-text-captions-and-si)
- [6. Apply statistical reporting discipline](#6-apply-statistical-reporting-discipline)
- [7. Run the paragraph necessity test](#7-run-the-paragraph-necessity-test)
- [8. Stop explanatory recursion](#8-stop-explanatory-recursion)
- [9. Audit claim repetition](#9-audit-claim-repetition)
- [10. Optional compression record](#10-optional-compression-record)
- [Non-negotiable exceptions](#non-negotiable-exceptions)

## 1. Separate evidence completeness from main-text completeness

Preserve the complete evidential record across the manuscript, figures, tables,
Methods, source data, and Supplementary Information (SI). Do not force that full
record into the main text. Reserve main-text space for evidence that establishes,
advances, or materially bounds the central claim.

Do not use compression to hide inconvenient evidence. If an observation changes
the direction, magnitude, scope, or credibility of the central conclusion, keep
it visible in the main text even if it is nominally a robustness or subgroup
analysis.

## 2. Classify every result before placement

When deciding where a result belongs, use these distinctions. Make a result-allocation table only if it helps a complex restructuring task or the user requests one. Placement depends on the actual article format; do not create SI or move material outside the requested edit scope.

| Class | Decision test | Default destination |
|---|---|---|
| `core_discovery` | Does it advance the paper's central conclusion? | Main text, with adequate evidence |
| `necessary_support` | Must the reader see it to accept the core discovery? | Main text briefly |
| `qualification` | Does it materially bound or alter the central interpretation? | Main text if yes; otherwise SI |
| `robustness` | Does it show the result survives an alternative specification, estimator, seed, threshold, or inference procedure without changing the conclusion? | SI, with a concise pointer when useful |
| `heterogeneity` | Is variation across groups, settings, tasks, or models itself part of the central claim? | Main text if central; otherwise SI |
| `provenance_detail` | Does it document traceability, preprocessing, implementation, or audit detail without advancing the conclusion? | Methods, Source Data, repository, or SI |
| `alternative_inference` | Does it test the same claim using a secondary inferential route? | SI unless it changes acceptance of the claim |
| `edge_case` | Does it define a failure boundary that changes how the claim must be read? | Main text if interpretation changes; otherwise SI |

Classify by function in this paper, not by analysis name. An ablation can be a
core discovery in a mechanism paper; heterogeneity can be the headline result;
a confidence interval can be the primary inferential evidence.

## 3. Build the shortest sufficient evidence chain

After classification, write the minimum ordered chain that lets the reader:

1. understand the central observation
2. see the decisive comparison or mechanism evidence
3. judge the primary uncertainty or inference
4. understand any boundary that changes the conclusion

Do not reproduce the chronological record of analyses. Route supporting checks
to SI with stable pointers when the article permits it and restructuring is authorized. Draft from the supplied evidence; a result-allocation table is not a prerequisite.

## 4. Prevent revision accretion

When an addition overlaps existing text, check the affected paragraph:

1. State what new function the proposed sentence serves.
2. Find existing sentences that already serve that function.
3. Prefer replacement, combination, or compression before appending.
4. Re-read the paragraph after the edit and delete any sentence made redundant.
5. Check that the change preserves the evidence and conditions needed here.

For reviewer-driven edits, ask:

> Does this sentence tell the reader what was discovered, or does it mainly tell
> a reviewer why an objection does not overturn the result?

Keep the first in the main text when necessary. Route the second to SI or the
response letter unless the objection is essential to the central inference.
Answer every reviewer fully in the response letter even when the manuscript
change is deliberately short.

## 5. Separate main text, captions, and SI

- **Main text:** what was found, the decisive support, and what it means for the
  central claim.
- **Figure or table caption:** what is shown and how to read it, including
  definitions needed to interpret the display.
- **SI:** why the conclusion survives deeper scrutiny, including secondary
  analyses, robustness, implementation detail, extended diagnostics, and
  non-central edge cases.

Do not repeat a full set of effect sizes, confidence intervals, and P values in
both the main text and caption. Choose one authoritative location for the full
numeric report and use the other location for the minimum narrative or reading
cue. Preserve journal-mandated caption content.

## 6. Apply statistical reporting discipline

Write from completed analyses and retain required statistical information. If the supplied material lacks an analysis needed to support a claim, identify the gap; a writing request does not authorize running new analyses. In the main text, normally report:

- the descriptive quantity needed to understand the effect
- the primary inferential statistic or interval needed to support the claim

Route secondary intervals, alternative estimators or inference procedures,
multiplicity checks, sensitivity analyses, and model-level heterogeneity to SI
unless they change the conclusion or are required in the main text. Never select
only the most favorable statistic. Preserve the reported analysis family and make relocated evidence findable.

## 7. Run the paragraph necessity test

When a Results paragraph seems redundant, ask:

> If this paragraph were removed, would the reader still understand and have
> adequate evidence for the paper's central claim?

- **No:** keep it.
- **Yes, but a reviewer might ask for it:** route it to SI or the response letter.
- **Yes, and the point appears elsewhere:** delete it.

When only one sentence is necessary, keep that sentence and relocate the rest.
Do not preserve an unnecessary paragraph merely because one clause matters.

## 8. Stop explanatory recursion

Remove explanations that merely restate an explanation. Keep the context needed to understand a result, even when it takes several sentences. Move extended technical reconciliation to SI only when readers can still assess the main inference and its boundaries without it.

## 9. Audit claim repetition

A major claim may be introduced, demonstrated, and synthesized, but each
appearance should help the reader in that location. If repetition is hard to untangle, compare the heading, transition, caption, Results, and Discussion; a claim-location map is optional. Useful labels are `introduce`, `demonstrate`,
`interpret`, `synthesize`, `shorten`, or `delete`.

Delete or compress restatements that add no new evidence, boundary, or
interpretation. Do not force the same full claim into every rhetorical slot.

## 10. Optional compression record

If the user asks for a compression record, choose the relevant items below. Do not generate or maintain these records by default:

1. **Result-allocation table:** result, class, effect on central interpretation,
   destination, and SI/caption pointer.
2. **Shortest evidence chain:** ordered main-text claims and their decisive
   evidence.
3. **Deletion log:** appended, replaced, compressed, relocated, or deleted text,
   with a short reason.
4. **Statistics-location record:** primary main-text report and secondary SI
   analyses.
5. **Claim-repetition map:** retained rhetorical function at each location.
6. **Word-count delta:** before and after for every revised Results subsection.

Otherwise return the requested prose, with only necessary notes about unresolved evidence or constraints.

## Non-negotiable exceptions

- Do not move information required for reproducibility, research integrity,
  participant safety, ethics, or a mandatory reporting checklist merely to save
  words.
- Do not bury contradictory or conclusion-changing evidence in SI.
- Do not strip a qualification that prevents a misleading causal, clinical,
  societal, or generalization claim.
- Do not remove statistics required by the target journal, study design, or
  field standard.
- When the user or editor explicitly requires a point in the main text, comply
  but still replace or compress neighboring redundancy before appending.
