---
name: questline
description: Collaboratively shape and implement the next bounded software deliverable within a scoped Questline, preserving settled intent in a numbered Waypoint and directional continuity in an agent-maintained Compass under `.questline/`.
---

# Questline

Each directory directly under `.questline/` is an active scoped goal. Work on one while accounting for the others. Its Waypoint is the user-facing record for the next deliverable, progressing from draft to accepted agreement; its Compass is agent-maintained directional memory.

Treat shared understanding as reached only when the user can evaluate what you say or record without reconstructing unstated context or reasoning. Make whatever is missing explicit at the depth needed for that evaluation; assent without understanding is not agreement.

Make the visual hierarchy of substantive replies reflect their conversational hierarchy. Distinguish what matters now from supporting context with the lightest suitable signposting, such as descriptive headings, lists, or emphasis; keep simple exchanges as plain prose.

## Reach Shared Understanding

Read every Compass, the selected Questline's Waypoints, the latest Waypoint from every other Questline, and enough project state to ground the conversation. On resumption, treat a marked draft as unaccepted; otherwise establish acceptance before implementing the latest Waypoint, and verified completion or explicit abandonment before allocating another identifier. Infer these from the conversation or project evidence; ask the user only if ambiguous.

Use an existing Questline when the work clearly advances it; otherwise establish one only for a goal the user intends to pursue now. Ask about placement only when ambiguity would materially affect scope or shared contracts. Create a new folder only with its first Waypoint.

Ask one decision at a time; keep alternatives on the same decision axis, and resolve prerequisite choices before presenting dependent ones.

Treat an initiating goal that does not already define the first deliverable as orientation. Begin with the direction-or-scope question whose answer would most change what should be delivered first. Wait for each answer and continue until it is clear what meaningful progress should look like now and which part of the goal the first deliverable should advance. Reflect that direction and rough scope for the user's agreement; do not propose or create a Waypoint before that framing is settled.

After the user approves making that framing the next Waypoint, create its draft and start with the consequential question whose answer would most change the deliverable. Investigate factual unknowns directly. For each consequential choice, explain the tradeoff and recommend a direction, then wait for the user's answer before following dependent branches. As each choice settles, keep the draft current with that intent while unresolved choices remain in conversation. Continue until the user has settled every consequential branch needed to define the result, proof, boundary, and commitments.

When those branches appear settled, stop searching for more questions and prepare the draft for acceptance.

Settle choices the deliverable depends on. Leave reversible implementation details to implementation and defer decisions that better evidence or a later Waypoint should inform. Do not inventory future branches.

Choose the smallest meaningful end-to-end result that advances the Questline and can realistically be implemented and reviewed in one sitting. Narrow uncertain scope; do not draft or order later Waypoints.

## Maintain Direction

Maintain each Questline's Compass at:

```text
.questline/<questline>/compass.md
```

with this title:

```md
# Compass
```

Create it with the first Waypoint and keep it aligned automatically when settled conversation or implementation learning clarifies durable direction. Use the Waypoint draft—not the Compass—to persist deliverable-specific decisions made while shaping it. The user neither authors nor separately approves the Compass. If learning calls for altering the agreed goal, a consequential boundary, or a shared contract with another Questline, settle the underlying choice with the user first.

Capture the destination and only boundaries that should shape how later Waypoints are chosen or judged. When a settled choice both defines the current deliverable and changes that longer-lived direction, record the concrete contract in the Waypoint draft and its directional consequence in the Compass. Do not copy a Waypoint's product or implementation contracts into the Compass merely because later work must respect them. Keep only enough to judge whether work is on course, never a project specification, roadmap, state summary, or implementation log. Ignore implementation-only learning. Preserve every abandoned Waypoint and every completed Waypoint the user has explicitly moved beyond—including any that precedes a later accepted Waypoint—as historical intent while the Questline remains active.

## Write the Waypoint

Keep at most one unfinished Waypoint per Questline. Allocate a local integer only when the user explicitly asks to make specified work the Questline's next deliverable or accepts your proposal to do so. That approval authorizes immediate draft creation and later updates that persist settled choices about the same deliverable; do not seek separate permission for either. Allocate a successor only after the current Waypoint is implemented and verified or explicitly abandoned. Authorization to perform the work, even when it is substantial or bounded, is not that choice. When work clearly merits a Waypoint, propose its boundary and ask the user whether to make it the next Waypoint. If the user declines, proceed with the requested work without changing `.questline/`. Pad the identifier to at least three digits and never renumber or reuse identifiers. Replace an unaccepted draft in place when its deliverable is discarded. If an accepted Waypoint is abandoned, record that outcome in its file so it remains historical intent.

```text
.questline/<questline>/NNN_snake_case_title.md
```

```md
# Waypoint NNN: Human-Readable Title

> Draft — not yet accepted
```

Match the identifier across title and filename, derive the slug from the title in lowercase snake case, begin with exactly one H1, and keep the draft marker shown above directly below it until explicit acceptance. Beyond that marker, the draft has no fixed schema and may remain incomplete while choices are open. Keep it current with the settled intent so far. Before acceptance, use the smallest natural structure that makes clear:

- the result and how it advances or tests the Compass;
- the evidence that distinguishes reached from not reached;
- consequential commitments, boundaries, limitations, and accepted risks;
- deliberately deferred adjacent decisions when silence could invite premature commitment, with a revisit trigger when useful.

Write settled intent, not unresolved alternatives, a discussion log, an implementation plan, or a future-feature catalog. Include detail only to remove material ambiguity or preserve a consequential decision. Trace every Waypoint claim to settled intent or a verified consequence the deliverable depends on; do not turn comparison examples or incidental consequences into requirements. State every commitment this deliverable depends on directly; references to another Questline are context only.

## Fortify and Continue

Before presenting the draft for acceptance, confirm the Waypoint is one meaningful result with unambiguous proof, settled consequential choices, proportionate commitments, and agreement with its Compass and naming convention.

Compare the selected Compass and proposed Waypoint with every other Compass and latest Waypoint. Where they suggest overlap, inspect only older relevant Waypoints or project state. Surface material duplication, contradiction, dependency, or incompatible shared contracts before approval. Bring choices about competing priorities or shared contracts to the user; reconcile the rest without turning this into a project-wide architecture review. Code overlap alone is not a conflict. Repeat this check before recording a Compass change arising from the draft.

Present only the completed draft for review and keep its file current with each settled revision until the user explicitly accepts it. On acceptance, remove its draft marker; only then is it the accepted implementation agreement. Begin no implementation before that transition.

When requested implementation or later verification, correction, refinement, or simplification continues the same bounded deliverable and the user has not explicitly selected a new-Waypoint boundary, work against the current accepted Waypoint. Never reopen an abandoned or historical Waypoint. Reconcile non-material learning into the current Waypoint as needed to keep the accepted deliverable accurate. If work on that deliverable would materially change its result, proof, public contract, boundary, consequential commitments, or accepted risks, stop implementation, restore its draft marker before revising it, return to shared understanding, and regain acceptance before proceeding. If the work instead forms a genuinely new bounded deliverable, do not fold it into the current Waypoint; follow the allocation rule above. Do not expand the current Waypoint with adjacent features. Apply the same Compass rule throughout implementation.

After implementing a Waypoint, review it from three perspectives, dispatching independent reviewers in parallel when supported and using separate review passes otherwise: correctness, maintainability, and any material security or performance concerns raised by the change.

The maintainability review should favor the simplest clear solution: fewer layers, convention over configuration, and no speculative edge-case handling. It should also verify affected tests against applicable testing instructions and project guidance.

Address the findings and repeat the reviews until no actionable findings remain.

Treat the Waypoint as verified only when every perspective reports no actionable findings on the same final state of the complete, integrated implementation.

Once the result is implemented and verified, keep the Waypoint current and return control without planning the next one.
