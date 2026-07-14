---
name: questline
description: Collaboratively shape and implement the next bounded software deliverable within a scoped Questline, preserving settled intent in a numbered Waypoint and directional continuity in an agent-maintained Compass under `.questline/`.
---

# Questline

Each directory directly under `.questline/` is an active scoped goal. Work on one while accounting for the others. Its Waypoint is the user-facing agreement for the next deliverable; its Compass is agent-maintained directional memory.

Treat shared understanding as reached only when the user can evaluate what you say or record without reconstructing unstated context or reasoning. Make whatever is missing explicit at the depth needed for that evaluation; assent without understanding is not agreement.

Make the visual hierarchy of substantive replies reflect their conversational hierarchy. Distinguish what matters now from supporting context with the lightest suitable signposting, such as descriptive headings, lists, or emphasis; keep simple exchanges as plain prose.

## Reach Shared Understanding

Read every Compass, the selected Questline's Waypoints, the latest Waypoint from every other Questline, and enough project state to ground the conversation. On resumption, establish acceptance before implementing the latest Waypoint, and verified completion or explicit abandonment before allocating another identifier. Infer these from the conversation or project evidence; ask the user only if ambiguous.

Use an existing Questline when the work clearly advances it; otherwise establish one only for a goal the user intends to pursue now. Ask about placement only when ambiguity would materially affect scope or shared contracts. Create a new folder only with its first Waypoint, after exploratory framing.

Ask one decision at a time; keep alternatives on the same decision axis, and resolve prerequisite choices before presenting dependent ones.

Treat an initiating goal that does not already define the first deliverable as orientation. Begin with the direction-or-scope question whose answer would most change what should be delivered first. Wait for each answer and continue until it is clear what meaningful progress should look like now and which part of the goal the first deliverable should advance. Reflect that direction and rough scope for the user's agreement; do not shape a candidate before it is settled.

Once the user agrees to that framing, start with the consequential question whose answer would most change the deliverable. Investigate factual unknowns directly. For each consequential choice, explain the tradeoff and recommend a direction, then wait for the user's answer before following dependent branches. Continue until the user has settled every consequential branch needed to define the result, proof, boundary, and commitments. Only then shape and write the Waypoint.

When those branches appear settled, briefly suggest drafting the Waypoint for review rather than searching for more questions.

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

Create it with the first Waypoint and keep it aligned automatically when settled conversation or implementation learning clarifies durable direction. The user neither authors nor separately approves it. If learning calls for altering the agreed goal, a consequential boundary, or a shared contract with another Questline, settle the underlying choice with the user first.

Capture the destination and only boundaries that should guide more than one Waypoint—enough to judge whether work is on course, never a project specification, roadmap, state summary, or implementation log. Ignore implementation-only learning. Preserve completed or abandoned Waypoints as historical intent while the Questline remains active.

## Write the Waypoint

Keep at most one unfinished Waypoint per Questline. Allocate the next local integer only after the current Waypoint is implemented and verified or explicitly abandoned; pad it to at least three digits and never renumber or reuse identifiers. Replace an unaccepted proposal in place when its deliverable is discarded. If an accepted Waypoint is abandoned, record that outcome in its file so it remains historical intent.

```text
.questline/<questline>/NNN_snake_case_title.md
```

```md
# Waypoint NNN: Human-Readable Title
```

Match the identifier across title and filename, derive the slug from the title in lowercase snake case, and begin with exactly one H1. The rest has no fixed schema: use the smallest natural structure that makes clear:

- the result and how it advances or tests the Compass;
- the evidence that distinguishes reached from not reached;
- consequential commitments, boundaries, limitations, and accepted risks;
- deliberately deferred adjacent decisions when silence could invite premature commitment, with a revisit trigger when useful.

Write settled intent, not a discussion log, implementation plan, or future-feature catalog. Include detail only to remove material ambiguity or preserve a consequential decision. State every commitment this deliverable depends on directly; references to another Questline are context only.

## Fortify and Continue

Confirm the Waypoint remains one meaningful result with unambiguous proof, settled consequential choices, proportionate commitments, and agreement with its Compass and naming convention.

Compare the selected Compass and proposed Waypoint with every other Compass and latest Waypoint. Where they suggest overlap, inspect only older relevant Waypoints or project state. Surface material duplication, contradiction, dependency, or incompatible shared contracts before approval. Bring choices about competing priorities or shared contracts to the user; reconcile the rest without turning this into a project-wide architecture review. Code overlap alone is not a conflict. Repeat this check before recording a Compass change after approval.

Present only the Waypoint for review and revise it until accepted. Begin no implementation before acceptance.

When implementation is requested, work against the accepted Waypoint. If implementation reveals a material change to its result, proof, boundary, or consequential commitments, return to shared understanding, revise it, and regain acceptance before proceeding. Do not expand it with adjacent features; leave those for the next Waypoint. Apply the same Compass rule throughout implementation. Once the result is implemented and verified, preserve the Waypoint and return control without planning the next one.
