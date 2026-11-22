# SOLACE Network — Project Management Policy

**Status:** Adopted workflow; revised 2026-11-22  
**Scope:** SOLACE Network projects, initially SOLACE Garden, PlantDB, and the future Support Site. Does not include FreeTV or EM3K.

## Purpose and systems of record

SOLACE uses a two-system approach:

- **GitHub master roadmaps** are the authoritative, complete, approved sequence of milestones—past, current, and future. Each milestone stays listed, including completed ones, with concise scope, status, dependency/sequence information, and a link to its historical acceptance record where applicable. Roadmaps define *what* is planned and *in what approved order*, not a running transcript of past implementations.
- **monday.com** is the operational source of truth for current milestone status, execution order, and progress for items on its board. While capacity allows, track the **entire approved project roadmap**, including completed milestones—not merely a rolling window. Owner, due-date, and timeline fields are optional, not required. The SOLACE Network board is at https://solacenetwork.monday.com/boards/18441033996.
- **GitHub technical documents** (GOALS, TECH_SPEC, UI_REDESIGN, test notes, decision records and code) remain authoritative for requirements, architecture, implementation, and acceptance criteria.
- **GitHub milestone-history documents** provide durable, evidence-backed records of accepted work **as milestones are completed**, regardless of whether corresponding monday.com items remain on the board. Garden's archive is [MILESTONE_HISTORY.md](https://github.com/solacenetwork/solace-garden/blob/main/docs/MILESTONE_HISTORY.md).

Do not maintain competing detailed status checklists in multiple locations. Maintain concise status in the master roadmap for completeness, live operational status in monday.com, and detailed completion evidence in the project's milestone-history document. Preserve technical decisions and history when condensing a roadmap; transfer records and verify links before removing original details.

## Sequence and dependencies

1. Execute milestones **in the explicitly approved roadmap order**, not by choosing whichever task is easiest or most convenient. Prerequisite and dependency ordering is intentional.
2. A milestone can be inserted, split, removed, deferred, or reordered **only through an explicit roadmap revision** before execution. Record the change and its consequences.
3. Preserve stable, namespaced identifiers. For example, **GARDEN-UI-8A4** (UI redesign Wizard navigation) is distinct from **GARDEN-V1-8A** (previously completed Storage Foundations) and **GARDEN-V1-8G** (the next feature milestone after UI redesign).
4. A planned start date is not a promise. Quota resets or other resource limits may affect scheduling without changing the approved milestone order.
5. Only accepted work unlocks the next dependent milestone. An implementation reported complete by an assistant or agent is not automatically accepted.

## Full-board tracking now; rolling window only if necessary

- Use the existing **SOLACE Network** board for SOLACE projects only. **Track every approved milestone for each active project while the plan has sufficient capacity**, including completed milestones. Organize substantial parallel sequences (e.g., Garden V1 features and its post-8F UI redesign) in separate groups. Do not delete completed items merely to keep the board small.
- The current planning assumption is a **200-item Free-plan ceiling**; this is a capacity planning constraint, **not an independently verified statement about current monday.com billing or archive rules**. Before any capacity-driven pruning, check the account's actual limit and whether archived items, subitems, or other item types count. Retain a sensible reserve for Garden, PlantDB, Support, and other approved SOLACE work.
- **When the board approaches a verified capacity constraint**, explicitly switch to a **capacity-based rolling milestone window**. Keep enough recently accepted milestones, active work, and upcoming approved milestones to preserve useful visual context across projects. The size of the window is flexible; there is **no mandatory two-behind/two-ahead rule**.
- In rolling mode, retire the **oldest accepted items first**, only when their GitHub roadmap entries and detailed milestone-history records are complete and checked. Review the item's notes, updates, comments, links, and attachments for unique information before removing it; transfer anything historically important to GitHub. An incomplete transfer leaves the monday.com item in place. Never retire unaccepted work merely because it is old.
- The GitHub master roadmap retains **all approved milestones and their order** even when monday.com shows only a rolling window. A retired board item is not a canceled milestone; it may be recreated from the roadmap if needed. Do not remove historical records from GitHub when freeing board capacity.
- **Main Table** is the full inventory and ordered planning view; **Kanban** is the visual working-buffer and dependency view described below. Gantt, paid timelines, and native automations must not be prerequisites.
- Track each item using its stable namespaced milestone ID, status, execution order, and link to the authoritative GitHub specification. Use optional notes and priority when useful, but avoid copying extensive technical checklists into monday.com or creating unnecessary subitems. Dates and owner assignments are not required for a self-directed project.
- No monday.com item retirement is authorized by this policy update alone; changing from full-board tracking to rolling mode is a separate, deliberate action.

## Kanban as a working buffer

The **Main Table** shows the complete approved milestone inventory. The **Kanban view** shows what SOLACE is concentrating on, **not** how many milestones are being coded simultaneously. Kanban status is a planning classification; the GitHub roadmap and its dependencies always control execution order.

- **In Process — current working buffer:** The set of approved milestones comprising the current phase. Items can be in this column before implementation begins. Work through them **sequentially in roadmap order**, applying the acceptance gate to each one; marking an individual item Done does not complete the entire buffer.
- **Blocked — dependency gate:** Milestones that cannot proceed until prerequisites are accepted (for example, later Garden features depending on completion of the UI redesign and Media/Gallery). The next milestone remains blocked until its own dependencies are satisfied. Being scheduled for later is not automatically the same as being blocked; identify the relevant dependencies in GitHub.
- **Future Work — outside the current focus:** Approved longer-horizon or separate-project work not yet admitted to the working buffer. Ideas without approved milestones belong in the project's Parking Lot instead.
- **Not Started — approved but not yet brought into the current buffer:** Keep work visible without implying that it is under active implementation. Move it into the working buffer when appropriate and dependency order allows.
- **Done — accepted:** Developer-confirmed milestone acceptance, with evidence recorded in GitHub. The Done column may be manually arranged for readability; card placement does not replace the roadmap's execution order.

A project-level umbrella item such as **Garden** can represent the overall project while its individual milestone items are tracked separately. Treat it as an overview, **not** another executable milestone, even if it appears in the In Process column.

**Current Garden example:** The post-8F UI redesign milestones form the In Process working buffer; start with UI 8A4 and then follow the approved UI sequence through Step 10. The original V1 feature pipeline resumes afterward according to [Garden's roadmap](https://github.com/solacenetwork/solace-garden/blob/main/docs/ROADMAP.md); downstream work remains gated by its specific dependencies. Do not interpret the number of In Process cards as concurrent engineering work or automatically shift a whole phase to Done when one milestone is accepted.

## Execution and acceptance

1. Take the next unaccepted milestone in the approved sequence from the master roadmap.
2. Confirm its specification and acceptance conditions in GitHub, then work on it in the existing development workflow (including Codex, Copilot, automated testing, and developer review as relevant).
3. Keep monday.com aligned with the agreed working buffer and dependencies. **In Process** can include queued milestones in the current phase; it does not claim active coding of every card. Use **Blocked** for work awaiting prerequisites and move an item to **Done** only after acceptance.
4. **Acceptance gate:** Record the developer's acceptance after necessary tests and manual checks. Do not mark accepted solely on an agent's completion report.
5. Mark the monday.com item **Done** only on acceptance, not just code completion.
6. Keep the milestone in the **complete GitHub roadmap** with its accepted status, concise scope and a link to its historical record. Add the evidence to the project-specific **MILESTONE_HISTORY.md**: stable ID, confirmed acceptance date if known, succinct outcome, commit/PR references, reported versus independently verified tests, relevant specification links, and caveats. Archive the details even while its monday.com item remains.
7. Keep the accepted item marked **Done** in monday.com for visual history while board capacity allows. If rolling mode is later explicitly adopted, perform the record-preservation and verification checks described above **before** retiring accepted items.

Removing completed monday.com items in a future rolling window is a board-capacity operation, **not** deletion of project history. The complete roadmap and durable acceptance evidence must survive regardless of board size.

## Parking Lot — uncommitted ideas

- **Ideas without an approved milestone belong in the relevant project's `PARKING_LOT.md`**, not in the monday.com execution pipeline. This includes feature suggestions, experiments, research questions, design alternatives, and potential future enhancements.
- A Parking Lot entry is **not a development commitment**, assigned priority, due date, or authorization to interrupt the current milestone. Ideas may remain deferred indefinitely or be discarded.
- Capture a concise description and any useful supporting links or context, without requiring a complete technical specification or creating a monday.com item.
- **Promotion requires an explicit decision:** agree that the idea should be implemented, define an appropriate milestone scope and acceptance conditions, establish dependencies and an approved place in the sequential roadmap, update the master roadmap and relevant technical documents, then create or update its monday.com milestone entry. Do not silently promote ideas as part of unrelated work.
- If new work changes an already approved milestone, revise that milestone and its execution sequence explicitly, documenting the effect on dependencies before proceeding.
- Brainstorming and research can continue while a milestone is in progress, but do not divert implementation merely because a new idea has appeared.

## Milestone-first planning

- **Milestones are commitments to outcomes, not calendar dates.** Use their approved sequence and acceptance gates to track progress; do not invent deadlines or dates for a self-directed open-source project.
- Dates, ownership, and scheduling fields are optional and should be used only when they convey meaningful information (for example, an actual external dependency). The board's visual emphasis should be on milestone identity, execution order, status, and GitHub references.
- Review monday.com first for the current milestone and operational progress, then consult GitHub for the authoritative ordered backlog and technical requirements. When a milestone is accepted, update monday.com and the relevant GitHub records as needed.

## Garden-specific transition

Garden is in the **post-8F UI redesign** tracked in [UI_REDESIGN.md](https://github.com/solacenetwork/solace-garden/blob/main/docs/UI_REDESIGN.md). As of November 22, 2026, **UI 8A1–8A3 are accepted**, and **UI 8A4** is the next implementation slice. Complete **UI 8A4–8A9, UI 8B, UI 9, and UI 10** in approved order. **Then return to the separate V1 feature roadmap at 8G**, followed by 8H and later milestones. The two sequences bearing “8A” are unrelated.

Garden's accepted implementation evidence has begun moving from [ROADMAP.md](https://github.com/solacenetwork/solace-garden/blob/main/docs/ROADMAP.md) to [MILESTONE_HISTORY.md](https://github.com/solacenetwork/solace-garden/blob/main/docs/MILESTONE_HISTORY.md). The roadmap still lists the full approved sequence with concise status and references; the milestone-history archive preserves prior detailed completion reports. Retaining completed milestones on monday.com remains the default while capacity permits.

## Changes to this policy

Revisit board structure and capacity when actual usage approaches the verified account limit. Full-board tracking is the present default, not a mandate to pay for additional capacity. Record any decision to adopt rolling mode here before changing how accepted items are retired; it does not change GitHub's master-roadmap authority.
