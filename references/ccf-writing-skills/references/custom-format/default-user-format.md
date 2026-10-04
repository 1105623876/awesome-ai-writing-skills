# Optional Source-Author Writing Format

Use this format only when the current user explicitly chooses the source author's LLaVA-4D/VGGT exemplar approach. An unspecified venue does not activate it. The historical filename is retained for provenance; this is not the default for general or academic writing.

## Source Exemplars

The current custom format is distilled from two source-author-selected exemplar cards:

- ICLR family: `references/exemplars/cards/llava-4d.md`
- CVPR: `references/exemplars/cards/vggt.md`

These examples describe the source author's preferences, not the current user's. Read only the card relevant to the chosen task.

## Writing Shape

This optional structure suits some method-centered vision papers. Adapt or omit steps when the current research calls for a different argument:

1. Task and capability gap: begin from a concrete capability the field cares about, then show why current systems fail in a physical, dynamic, geometric, or deployment-relevant setting.
2. Prior-work ladder: present prior work as successive partial progress, not as a citation list.
3. Root challenge: identify the missing representation, missing output family, missing temporal/spatial reasoning, or missing direct prediction path.
4. Core insight: express one observation that makes the method feel inevitable.
5. Mechanism preview: name the main modules by their roles in the story.
6. Evidence promise: map each contribution to a measurable task, ablation, benchmark, qualitative example, or downstream use.
7. Boundary: explicitly avoid claims that require an actual target venue, uncollected experiments, or unsupported novelty.

## Section Defaults

Abstract:

- One sentence for the capability gap.
- One sentence for the limitation of current approaches.
- Two to three sentences for method mechanism and outputs.
- One sentence for dataset, benchmark, or evaluation package if present.
- One sentence for results or expected evidence, calibrated to the actual proof available.

Introduction:

- Paragraph 1: field momentum and why the problem matters.
- Paragraph 2: prior-work ladder and remaining failure mode.
- Paragraph 3: root observation or design insight.
- Paragraph 4: method overview with modules and output definitions.
- Paragraph 5: contribution bullets, each linked to evidence.

Method:

- Define inputs and outputs before architecture.
- Explain the representation or token family before fusion or training details.
- Separate model, data, training, and inference if all exist.
- Use module names that reflect reviewer-facing function.

Experiments:

- Main comparison first.
- Then ablations tied to contribution bullets.
- Then qualitative examples that expose the motivating failure mode.
- Then efficiency, scaling, or downstream evidence if claimed.
- Then limitations and failure cases.

## Closed-Loop Generation

Only if the user requests iterative simulated review, select suitable steps from `references/expert-review-loop.md`. Merely choosing this format does not require review, scoring, or multiple drafts:

1. Draft using this custom format.
2. Select the requested reviewer views, such as method, experiment, or writing/storyline perspectives.
3. Assign a provisional score with reasons only if scoring was requested; prefer the supplied venue scale.
4. Revise high-severity issues first: unclear contribution, unsupported evidence, missing outputs, weak baselines, overclaiming, or format drift.
5. Re-review the revision.
6. Repeat only within the requested revision scope and number of rounds; report unresolved issues that need new evidence or user decisions.

## Output Contract

For a requested full format-and-review demonstration, the following are possible outputs. Otherwise return only the requested draft, revision, or advice:

1. Explicitly chosen exemplar format.
2. Loaded custom exemplars.
3. Global story blueprint.
4. Draft or revision.
5. Claim-evidence map.
6. Review score and critique.
7. Revision pass and re-review score.

## Maintenance

The exemplar list can be edited when the user requests it. No separate curator skill is required or automatically invoked; preserve source attribution when adding cards.
