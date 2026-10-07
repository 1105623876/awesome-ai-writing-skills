# Nature Results–Discussion Corpus Guidance

> Adapted for ai-writing on 2026-10-07 from [upstream](https://github.com/Yuan1z0825/nature-skills/blob/7d5f160ebfe8033375b4afef7c5911aa4203c983/skills/nature-shared/core/nature-results-discussion.md).
> Modified scope, task boundaries, fixed structures, and mandatory audits; retained detailed guidance and examples. License: [Apache-2.0](../LICENSE).

Use this reference when drafting, restructuring, or polishing Results and
Discussion for flagship **Nature**, **Nature Communications**, **Nature Machine
Intelligence**, or another **Nature Portfolio** title. The patterns were
initially distilled from an author-supplied NMI reading set and reinforced by a
second author-supplied comparison set of flagship Nature papers. They are
generalized here as Nature-style defaults and remain **corpus-derived writing
guidance, not official journal requirements**. Current target-journal
instructions, article-type rules, reporting standards, and the paper's actual
evidence always take precedence.

## Contents

- [Core division of labour](#core-division-of-labour)
- [Build Results as claim escalation](#build-results-as-claim-escalation)
- [Choose an evidence-chain archetype](#choose-an-evidence-chain-archetype)
- [Prevent same-level repetition](#prevent-same-level-repetition)
- [Prefer diagnostic experiments when mechanism matters](#prefer-diagnostic-experiments-when-mechanism-matters)
- [End evidence units with an inference](#end-evidence-units-with-an-inference)
- [Apply the local-interpretation gate](#apply-the-local-interpretation-gate)
- [Write Discussion as synthesis, not re-demonstration](#write-discussion-as-synthesis-not-re-demonstration)
- [Optional Results and Discussion check](#optional-results-and-discussion-check)

## Core division of labour

- **Results:** establish and advance the paper's scientific claims through an
  evidence chain. Results may include comparison, ablation, perturbation,
  robustness, failure analysis, directly evidence-bound interpretation, and a
  local inference.
- **Discussion:** synthesize several established claims into a higher-order
  understanding, relate that understanding to prior work, explain its
  importance, and bound its implications.

Do not enforce the mechanical split `Results = facts only` and
`Discussion = all interpretation`. The operative boundary is local versus
synthetic interpretation: keep an explanation in Results when it directly
resolves the experiment just reported; move broader theory, literature
integration, general implications, and extended speculation to Discussion.

## Build Results as claim escalation

Give each Results subsection a clear question and evidential role. Independent replications, negative results, and parallel analyses need not each establish a stronger new claim. Prefer a conclusion-bearing heading over a procedural experiment
label when the evidence supports it.

When results depend on one another, this order can help:

`observation -> unresolved question -> targeted experiment -> comparison or perturbation -> local interpretation -> stronger claim -> next question`

A mechanism-focused paper may use an arc such as:

`phenomenon -> source -> necessary condition or mechanism -> decomposition -> boundary or robustness`

Do not substitute repeated demonstrations of the same claim for escalation.
Two subsections may share data, conditions, or methods; they become redundant
when they repeat the same evidence without adding useful support, scope, or interpretation. Independent corroboration can be necessary even when the conclusion is unchanged.

## Choose an evidence-chain archetype

Organize Results around the evidence needed for the contribution. A system description, benchmark, or ablation may be essential for a methods or resource paper. The following archetypes offer alternatives when the current structure obscures the argument; none is mandatory:

### Discovery loop

Use when evidence changes what should be tested next:

`initial hypothesis -> real or decisive test -> analyse the resulting evidence -> refine the hypothesis -> next test -> architecture or mechanism validation`

The Results should preserve the epistemic loop without becoming a chronological
lab notebook. Keep only iterations that change the claim or the next scientific
question.

### Core capability and validation envelope

Use when the paper establishes one central capability, then asks whether it is
reliable, safe, general, or confounded:

`establish core capability -> validate in decisive settings -> test safety or bias -> rule out central alternatives -> define limits`

Treat medication, subgroup, decision, bias, or perturbation analyses as the
validation envelope of the main story when they answer whether the same core
capability survives important conditions. Do not present each check as an
unrelated second discovery.

### Capability ladder

Use when a system or model supports progressively stronger claims:

`quantitative performance -> robustness to data properties -> stronger competitors or tuned ensembles -> interpretability -> broader foundation or transfer abilities`

Each rung must justify a stronger inference. More datasets or another benchmark
at the same inferential level do not automatically create a new rung.

Across archetypes, the most common functional chain is:

`establish the phenomenon -> stress-test it -> rule out alternatives -> broaden it -> interpret it -> bound it`

Not every paper needs every move. Preserve the shortest chain sufficient for
the central claim.

## Prevent same-level repetition

A later subsection may reuse an earlier baseline, control, or reference
contrast, but it must not present the same comparison and conclusion as a new
result. Treat reused conditions as **necessary comparators**, not as the centre
of the later subsection.

Ask what deeper discriminator the later analysis adds:

- content versus correct correspondence
- association versus necessity
- nominal performance versus robustness
- apparent gain versus a data, compute, or tuning confound
- one setting versus the boundary of generalization

Make the new perturbation, falsification, stronger comparator, or boundary test
the subsection's decisive evidence when present. If adjacent subsections both say `X helps`, first check whether they provide independent corroboration or different scope. Merge only redundant content, within the authorized restructuring scope. A possible progression is:

`X is associated with the effect -> disrupting the proposed relation removes the effect -> therefore the relation, not merely the presence of X, is necessary within the tested design`

## Prefer diagnostic experiments when mechanism matters

When explaining a mechanism claim, look for completed tests that distinguish explanations rather than relying on a with/without comparison alone. Relevant evidence may include perturbing, shuffling, masking, misaligning, or removing the proposed information and measuring the predicted effect. Describe only tests actually supplied. Suggest new tests only when research guidance is requested; do not present planned tests as results.

Use the logic:

`association -> targeted disruption -> predicted degradation -> bounded mechanism inference`

Do not turn this pattern into automatic causal language. Calibrate the
inference to the intervention, controls, design, and alternative explanations.

## End evidence units with an inference

After a coherent group of measurements, state what the evidence establishes;
do not stop at a sequence of numbers. The inference must be no broader than the
evaluated conditions.

Report failures, reversals, anomalous scaling, weak subgroups, and performance
trade-offs when they materially define where the claim holds, weakens, or
fails. Do not hide a conclusion-changing boundary in Supplementary
Information.

Place robustness in the main text when it establishes a necessary condition,
rules out a central alternative, reveals a failure boundary, or otherwise
creates an independent scientific inference. Route it to SI when it only adds
reassurance that the same conclusion survives another seed, estimator,
threshold, or secondary specification.

## Apply the local-interpretation gate

Results may use calibrated language such as `suggests`, `indicates`, `likely
because`, `probably owing to`, or `we speculate that` only when all of the
following hold:

1. the interpretation answers the question raised by the immediately preceding
   result
2. the evidence for it is visible in the current subsection
3. uncertainty and alternative explanations remain explicit
4. the passage closes the local evidence unit instead of opening a broad field
   discussion

If several sentences are needed to reconcile theory, prior literature, or
competing mechanisms, state the bounded local inference in Results and move the
extended synthesis to Discussion or SI as appropriate.

## Write Discussion as synthesis, not re-demonstration

One possible order, when these functions are needed, is:

`brief central finding anchor -> cross-Results synthesis -> relation to prior work or theory -> importance -> boundary conditions and limitations -> broader implications or future directions`

Open with the problem, method, or finding that best restores context. A short recap with necessary anchor numbers can help. Continue with the interpretation and boundaries the paper actually supports; significance and future directions are not compulsory closing moves. Do not repeat the full comparison, effect
size, statistical test, and inference already used to demonstrate the claim in
Results.

Distinguish:

- **necessary recap / anchor:** `Results establishes X; taken together, X implies Y`
- **redundant re-demonstration:** Results and Discussion both replay
  `A versus B -> effect -> test -> therefore X`

Some published Nature Portfolio content types may use a Conclusion rather than
a standalone Discussion. Treat that as corpus variation, not permission to
ignore the current target-journal article-type instructions or an
editor-provided template.

## Optional Results and Discussion check

For requested structural review or unresolved repetition, use relevant questions below. A table or record is not required:

| Audit field | Question |
|---|---|
| Scientific question | What unresolved question does this subsection answer? |
| Claim or support | What proposition, corroboration, boundary, or negative finding does this add? |
| Evidence-chain role | Establish, stress-test, discriminate, broaden, interpret, or bound? |
| Decisive evidence | Which comparison, perturbation, or analysis establishes it? |
| Evidential value | What inference or necessary support would disappear if this were removed? |
| Next question | What uncertainty naturally motivates the following subsection? |

Compare adjacent subsections for redundant evidence, while preserving independent corroboration and distinct conditions. Relocate material only within the requested scope and permitted article structure.

When Discussion repeats Results, distinguish useful functions such as `anchor`, `synthesize`, `relate`, `bound`, or `extend`. Delete any
repetition that only re-demonstrates the Results evidence.
