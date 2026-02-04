---
name: Coordinator Mandate
description: Mandatory rule that every generated team must have a coordinator role
---

# Coordinator Mandate

## Applicability

- Applies to: All agents (all members of the design team must understand and follow this rule)

## Rule Content

### Coordinator Must Exist

Every generated team structure must contain at least one coordinator role. The coordinator's .md file is placed at the root level of the `agents/` directory (not inside subfolders).

### Coordinator Does Not Execute

The coordinator role is only responsible for: task planning, task assignment, progress tracking, quality control. The coordinator must not simultaneously undertake execution responsibilities of other agents in the team.

### Sub-Coordinator Rules

When a team's non-coordinator agent count exceeds 7, sub-coordinators must be introduced. Sub-coordinators are managed by the coordinator and manage agents within their group. Sub-coordinators may not perform execution work, but if their group has ≤ 3 agents, sub-coordinators are allowed to undertake a small amount of execution responsibilities.

## Violation Determination

- Generated team structure has no coordinator .md file in `agents/` root directory → Violation
- Coordinator's .md has execution work (non-coordination responsibilities) in the "Responsibilities" section → Violation
- Team has more than 7 non-coordinator agents but no sub-coordinators → Violation

## Exceptions

This rule has no exceptions.
