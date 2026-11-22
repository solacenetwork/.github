# SOLACE Network — Project Management Policy

**Status:** Adopted initial workflow (2026-11-21)  
**Scope:** SOLACE Network projects, initially SOLACE Garden, PlantDB, and the future Support Site. Does not include FreeTV or EM3K.

## Purpose and systems of record

SOLACE uses a two-system approach:

- **GitHub master roadmaps** are the authoritative, ordered, complete backlog of milestones (including milestones not yet in monday.com). They define *what* is planned and *in what approved order*.
- **monday.com** is the operational source of truth for the *status, owner, schedule, and progress* of items currently in its rolling working window. The SOLACE Network board is at https://solacenetwork.monday.com/boards/18441033996.
- **GitHub technical documents** (GOALS, TECH_SPEC, UI_REDESIGN, test notes, decision records and code) remain authoritative for requirements, architecture, implementation, and acceptance criteria.
- **GitHub milestone-history documents** provide durable records of accepted work once its monday.com item is retired.

Do not maintain competing detailed status checklists in multiple locations. During transition, existing Markdown completion evidence must remain intact. Never delete technical or historical details simply to simplify a roadmap.

## Sequence and dependencies

1. Execute milestones **in the explicitly approved roadmap order**, not by choosing whichever task is easiest or most convenient. Prerequisite and dependency ordering is intentional.
2. A milestone can be inserted, split, removed, deferred, or reordered **only through an explicit roadmap revision** before execution. Record the change and its consequences.
3. Preserve stable, namespaced identifiers. For example, **GARDEN-UI-8A4** (UI redesign Wizard navigation) is distinct from **GARDEN-V1-8A** (previously completed Storage Foundations) and **GARDEN-V1-8G** (the next feature milestone after UI redesign).
4. A planned start date is not a promise. Quota resets or other resource limits may affect scheduling without changing the approved milestone order.
5. Only accepted work unlocks the next dependent milestone. An implementation reported complete by an assistant or agent is not automatically accepted.

## Rolling monday.com window

- Use the existing **SOLACE Network** board, with project scope limited to SOLACE Network work. Start with a **target of approximately 60 in-window items account-wide**, leaving ample headroom beneath the Free plan's nominal 200-item limit.
- Include the current milestone and the next several milestones in sequence, plus selectively planned PlantDB or Support milestones when ready. Do **not** import all past completed milestones simply to remove them again.
- **Table** is the primary ordered planning view; **Kanban** is a supplementary status view. Gantt, paid timelines and native automations must not be dependencies of this workflow.
- Track each item with its stable milestone identifier, status, and link to the authoritative GitHub specification, plus optional priority, owner, date, or blocker. Use the board's existing columns where possible. Leave unknown dates blank rather than invent deadlines.
- Keep the board readable; do not mirror all technical checklist details or create unnecessary subitems.
- Before relying on the exact free-tier limit, or whether archived items/subitems count toward it, verify the currently applicable monday.com plan rules. This workflow does not require archival within monday.com.

## Execution and acceptance

1. Take the next unaccepted milestone in the approved sequence from the master roadmap.
2. Confirm its specification and acceptance conditions in GitHub, then work on it in the existing development workflow (including Codex, Copilot, automated testing, and developer review as relevant).
3. Update the monday.com status as work begins, is blocked, and moves through review.
4. **Acceptance gate:** Record the developer's acceptance after necessary tests and manual checks. Do not mark accepted solely on an agent's completion report.
5. Mark the monday.com item **Done** only on acceptance, not just code completion.
6. Update its master roadmap status and preserve completion evidence. Add or update the project-specific **MILESTONE_HISTORY.md** with stable ID, acceptance date, succinct outcome, commit/PR references, applicable specification links, and any known caveats.
7. **Only after verifying the GitHub records are committed**, remove the completed monday.com item to free capacity. Ensure nothing unique is lost from item notes, comments, attachments, or dates.
8. Pull the next pending milestone(s) from the master roadmap in their approved order. Replenish when useful; 60 is a target, not a mandatory batch size.

Deleting completed monday.com items is an intentional rolling-window operation, **not** deletion of project history. An incomplete archival operation must leave the monday.com item in place until resolved.

## Garden-specific transition

Garden is in the **post-8F UI redesign** tracked in [UI_REDESIGN.md](https://github.com/solacenetwork/solace-garden/blob/main/docs/UI_REDESIGN.md). At adoption, **8A1–8A3 are accepted** and **UI 8A4** is next (waiting for the planned Codex reset). Complete **UI 8A4–8A9, UI 8B, UI 9, and UI 10** in approved order. **Then return to the separate V1 feature roadmap at 8G**, followed by 8H and later milestones. The two sequences bearing “8A” are unrelated.

During the transition, keep the original [ROADMAP.md](https://github.com/solacenetwork/solace-garden/blob/main/docs/ROADMAP.md) and UI redesign record intact, including evidence and accepted-history sections. Simplification and relocation of older milestone records are separate, reviewed changes; no historical record should be discarded.

## Changes to this policy

Revisit board structure and capacity after the small pilot. Changes to the execution or archival process should be recorded here before altering established workflows.
