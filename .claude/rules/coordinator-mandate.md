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

### Flat Architecture

Every team must use a flat architecture: one coordinator directly manages all worker agents. Sub-coordinators are prohibited because they add context relay overhead and degrade information quality in Claude Code's Task tool.

When a team's non-coordinator agent count exceeds 7, split the team into multiple independent teams rather than adding sub-coordinators.

## Violation Determination

- Generated team structure has no coordinator .md file in `agents/` root directory → Violation
- Coordinator's .md has execution work (non-coordination responsibilities) in the "Responsibilities" section → Violation
- Team contains a sub-coordinator agent whose sole purpose is to coordinate other agents → Violation
- Team has more than 7 non-coordinator agents without being split into separate teams → Violation

## Exceptions

This rule has no exceptions.
