# Instructional Design Inventory & Gap Analysis

## Purpose
This audit summarizes what instructional-design elements already exist in the Lee-Tee prototype and what is currently missing to support consistent, scalable, standards-aligned episode development.

## Inventory: What Exists

### 1) Clear instructional architecture in the engine
- A formal episode schema defines section types (`sel-checkin`, `vocabulary`, `story`, `writing`, `reflection`) and activity types (`vocab-fill-blank`, `comprehension-quiz`, `drag-drop`, etc.).
- Layered section model (`core`, `expanded`, `supports`, `checks`, `media`) is documented and implemented as the baseline pattern.
- Basic schema validation exists for required fields and valid section types.

**Why this matters:** You already have a reusable pedagogical container for lesson flow and scaffolding.

### 2) Learning objective structures are present
- Episode config supports language + content objectives and standards tags.
- Episode 1 includes SIOP-style language/content objective statements and standards alignment.
- Engine component for rendering objectives and strategy lists exists.

**Why this matters:** The project has objective metadata and a UI path for objective display.

### 3) Instructional sequence is established in Episode 1
Episode 1 demonstrates a coherent sequence:
1. SEL check-in
2. Character choice (learner pathing flavor)
3. Vocabulary frontloading
4. Story/comprehension interactions
5. Strategy activity (guided + drag/drop)
6. Writing practice
7. Reflection/closure

**Why this matters:** This is a complete lesson arc you can replicate.

### 4) Engagement and supports are built in
- Points/badges/progress tracking are integrated.
- Multimodal supports exist (audio/read-aloud, visuals, interaction-heavy practice).
- Accessibility toggles are part of current parity expectations.
- Translation/i18n system exists across EN/ES/FR/HT with fallback behavior.

**Why this matters:** Strong foundations for UDL-style access and motivation are already present.

### 5) QA and parity documentation exists
- You already maintain parity checklists and integration plans for preserving Episode 1 behavior during engine migration.

**Why this matters:** There is process discipline around not breaking instructional behavior during refactors.

---

## Gaps: What’s Lacking

### A) No shared instructional design spec (cross-episode)
There is no single “Instructional Design Requirements” document that defines:
- required lesson phases,
- minimum checks-for-understanding per phase,
- acceptable scaffolds,
- evidence of mastery expected by end of episode.

**Risk:** New episodes may drift in quality and pedagogy.

### B) Episode 2 is instructional stub only
Episode 2 includes placeholder metadata and one “coming soon” section, but no implemented instructional sequence, checks, or practice progression.

**Risk:** Current architecture can’t be validated for cross-subject transfer (ELA -> Math).

### C) Objective-to-assessment traceability is weak
Objectives and standards are present, but there is no explicit objective-to-activity map showing:
- which activity assesses which objective,
- what completion criteria equals mastery,
- what remediation trigger should fire when learners miss.

**Risk:** Hard to prove instructional effectiveness.

### D) Inconsistent use of layer model in authored content
Layer concepts (`expanded`, `supports`, `checks`) are defined in schema guidance but are not consistently represented as explicit, reusable authoring patterns in every section.

**Risk:** Supports/checks can become ad hoc rather than systematic.

### E) No formal differentiation matrix
Character choice provides flavor/support differences, but there is no explicit matrix mapping learner needs to supports (e.g., multilingual newcomer, below-level reader, advanced learner).

**Risk:** Differentiation may feel thematic rather than intentional.

### F) Assessment/rubric artifacts are not standardized
While writing interactions and auto-check features exist, there is no shared rubric schema artifact (criteria, levels, feedback language, mastery thresholds) that is episode-agnostic.

**Risk:** Evaluation quality and feedback consistency vary episode-to-episode.

### G) Data instrumentation for instructional decisions is limited
Progress and completion are tracked, but there is little explicit analytics framing for instructional questions (e.g., “which misconception is most common at Step 3?”).

**Risk:** Hard to iterate pedagogy from evidence.

---

## “Fix This” Plan (Practical, Ordered)

### Phase 1 — Define the instructional contract (highest leverage)
1. Create `docs/INSTRUCTIONAL-DESIGN-SPEC.md` with non-negotiables:
   - required episode arc,
   - minimum supports/checks per section type,
   - mastery evidence requirements,
   - accessibility + language support minimums.
2. Add an objective-assessment mapping template for each episode.
3. Add rubric schema template for writing/reflection tasks.

### Phase 2 — Make the contract enforceable
4. Extend schema validation to warn/error when required instructional artifacts are absent (e.g., no checks layer in assessed sections).
5. Add a lightweight episode QA checklist that includes instructional quality criteria (not only technical parity).

### Phase 3 — Prove scalability with Episode 2
6. Fully implement Episode 2 using the same arc and traceability model.
7. Validate that each objective has:
   - at least one formative check,
   - one performance task,
   - remediation support.

### Phase 4 — Improve continuous improvement loop
8. Add event logging taxonomy for instructional decisions (misconceptions, retries, hint usage, language toggles).
9. Build a monthly instructional review ritual driven by those metrics.

---

## Immediate Next Actions (This Week)
- Draft the cross-episode instructional spec doc.
- Add objective-to-activity mapping table to Episode 1 and Episode 2 configs/docs.
- Convert Episode 2 from stub to at least 4 real instructional sections.
- Add validator checks for missing `checks`/`supports` expectations in assessed sections.

If you want, next I can produce the actual first draft of `INSTRUCTIONAL-DESIGN-SPEC.md` and a concrete Episode 2 scope that fits your current engine without major rewrites.
