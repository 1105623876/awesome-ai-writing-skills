# Writing Checklists

Use this file to prevent omissions during planning, drafting, revision, score lifting, and final readiness checks. Select only the checks relevant to the current request. A paragraph edit does not require a full-paper audit or a report of skipped checks; use the status template only when the user requests an audit record.

## Intake Checklist

- Use the supplied venue, track, and paper type when relevant. If no venue is given, follow the current discipline and writing task; do not assume the source author's custom format.
- Deadline pressure and desired output granularity are known: plan, rewrite, line edit, review, or final check.
- Available materials are listed: manuscript, appendix, figures, tables, reviews, code, experiments, references, style exemplars.
- Missing materials that affect confidence are named.
- Claims that cannot be verified from provided materials are not treated as facts.

## Venue And Style Checklist

- Venue family is mapped with `ccf-a-venue-map.md` when a CCF-A target is named.
- Venue expectations are selected from `venue-adapters.md` only for a specified venue.
- `custom-format/default-user-format.md` is used only if the current user chooses that exemplar format.
- Exemplar cards are used only for writing moves, not wording or technical content.
- Venue-specific evidence package is visible: baselines, ablations, proof, user study, systems evaluation, security threat model, visual evidence, or theory proof as appropriate.

## Whole-Paper Argument Checklist

Organize the argument around the contribution actually present: a finding, method, theory, resource, benchmark, protocol, system, or user-study insight. Do not imply a stronger contribution type than the evidence supports, and do not recast an accurate, ordinary contribution as a grand story.

Check:

- The problem is concrete enough for the venue's audience.
- Where the paper claims a gap, it explains why prior work leaves it open, not just "existing methods fail."
- The method, theory, or resource connects to that problem.
- The evidence package tests the central claim.
- Material boundaries are stated where they change interpretation.

Signals that the structure needs revision:

- The method appears before the reader understands the problem.
- The paper sells a module but experiments validate only the whole pipeline.
- The Abstract claims broad improvement but experiments cover a narrow setting.
- Related Work hides the strongest competitor.
- Experiments introduce claims never promised earlier.
- The conclusion adds new claims.
- Figures show many details but no clear message.

## Section Revision Checklist

- The section role is named before revision.
- Each paragraph has one main message.
- The first sentence of each paragraph signals that message.
- Terminology is stable across sections.
- Transitions show cause, contrast, consequence, refinement, or example.
- Figures and tables are introduced before interpretation.
- Captions state what the reader should learn.
- The section ends with the intended next-step logic when appropriate.

## Claim-Evidence Checklist

For every major Abstract, Introduction, and Conclusion claim:

```text
Claim:
Location:
Evidence:
Evidence type:
Support level: strong / adequate / weak / absent
Required action:
```

Rules:

- During language polishing, preserve claim strength and flag evidence gaps separately. Apply substantive claim changes only within the user's authorized revision scope.
- Supported claims may be sharpened within that scope.
- For weakly supported or unsupported claims, identify the evidence gap and suggest narrower wording, removal, or stronger evidence as appropriate.
- Evidence hidden only in the appendix must be signposted in the main text.

## Reviewer-Risk Checklist

Scan for:

- unclear contribution,
- weak novelty positioning,
- significance unclear for the venue,
- unsupported central claim,
- weak baseline,
- missing ablation, proof, user study, or system evaluation,
- unfair protocol or metric,
- reproducibility gap,
- figure/table readability issue,
- overclaim,
- generic limitation,
- ethics or responsible-research issue,
- venue mismatch.

## Score-Lifting Checklist

Use with `score-lifting-loop.md` when the task concerns known review scores or score diagnosis. A separate reviewer skill is optional and follows the current request; this checklist does not invoke it.

- Current stance or key reviewer concerns are stated; include a numerical score only when requested or needed to interpret existing scores.
- Target score or readiness threshold is stated only when supplied by the user; otherwise omit it.
- Top score blockers are ranked by severity.
- Each blocker has a fix class: writing-fixable, analysis-fixable, citation/positioning, figure/table, reproducibility, requires-new-result, accepted-limitation, or venue-mismatch.
- Writing-only fixes are separated from fixes requiring new experiments, proofs, studies, or baselines.
- When numerical scoring is relevant, expected score impact is attached only to concrete changes.
- After revision, the same reviewer concern is re-tested.

## Final Readiness Checklist

When asked for a final-readiness audit, check the relevant items below and report material unresolved issues. A local edit does not certify the whole paper:

- The intended discipline, document type, and any supplied venue/style requirements are clear.
- The global story is internally consistent.
- Central claims have visible support.
- Closest prior work and strongest baselines are handled.
- Venue-specific evidence is visible in the main paper.
- Limitations are honest and bounded.
- Reproducibility and ethics details are present where relevant.
- No high-severity issue remains unlabeled.
- The final answer states important findings and unresolved risks; a full status record is included only when requested.

## Minimal Checklist Status

Use this optional compact status when the user requests a checklist record:

```text
Checklist status:
- Venue/style:
- Storyline:
- Section roles:
- Claim-evidence:
- Reviewer risks:
- Score-lifting:
- Final readiness:
- Unresolved:
```
