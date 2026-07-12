# Questline

Questline pursues scoped software goals one bounded deliverable at a time. Each deliverable is captured in a **Waypoint** for you to review and approve.

The example below shows a project pursuing two goals at once. Each subdirectory is one active Questline:

```text
.questline/
├── message-delivery/
│   ├── compass.md
│   ├── 001_publish_through_rabbitmq.md
│   └── 002_receive_into_laravel_queues.md
└── billing-reliability/
    ├── compass.md
    └── 001_surface_reconciliation_failures.md
```

## Workflow

1. Invoke `$questline` and describe the goal you want to advance. The agent uses a matching Questline or starts one for a new goal.
2. Discuss one bounded deliverable until its result, proof, and boundaries are clear. The agent then writes the Waypoint to disk and revises that same file with you until you approve it.
3. Ask the agent to implement the approved Waypoint. If implementation reveals that the Waypoint needs to change, the agent revises it with you and waits for approval before continuing.
4. Repeat for the next Waypoint. When you stop pursuing the goal, remove its folder or preserve it elsewhere; every folder left in `.questline/` is active.

## Compass

Each Questline's `compass.md` is a short, living statement of its goal and durable boundaries. It keeps later Waypoints aligned and helps the agent detect conflicts across active Questlines without becoming a roadmap or project specification.

The agent creates and updates it from settled decisions and implementation learning that clarifies direction. You do not maintain or approve it separately; when direction itself needs to change, the agent discusses the underlying decision with you first.

## Pitfalls

- **Guessing through the fog of war.** Defer decisions the current Waypoint does not depend on; record a revisit trigger only when it prevents premature commitment.
- **Turning `.questline/` into a backlog.** Create a Questline only for work you intend to pursue now, and clean it up when you stop pursuing it.
- **Assuming concurrent Questlines are independent.** The agent surfaces conflicts automatically; you decide how competing priorities or shared contracts should be reconciled.
- **Letting a Waypoint grow.** Keep it focused on one bounded deliverable. Save adjacent features and follow-up work for the next Waypoint rather than expanding the current one.
