# Seven-Section Prompt Skeleton

Blank template: contains only structure, rules, and placeholders. When identifying gaps, read "Required Elements" to find what is missing; when assembling, copy the "Placeholders" block and replace the content inside 〈 〉, and the deliverable must not retain 〈 〉.

## General annotation rules

- [Assumption]: absent from the draft and filled in with a default value. [User confirmed]: content selected in the popup or entered free-form. [Unknown]: neither a source nor a default value; must not be fabricated.
- Any value absent from the draft (number, format, object, scope, tool) always carries an annotation, while merely reordering existing information needs none. The seven section headings use their original names and the body is written in English regardless of the draft's language; one piece of content belongs to only one section.

---

## Title line (first line of the block, not one of the seven sections)

- Required elements: task summary. This line answers: what is this whole task about, in the fewest words?
- Filling: 1 sentence, ≤30 characters, summarizing the object and the action of the whole task in English, with no section name and no annotation; put it on the block's first line with [Identity] starting on the next line; the host takes it verbatim to generate the session title.
- Placeholders:
  ```
  〈task summary〉
  
  ```

## [Identity]

- Required elements: executor role. This section answers: who executes, and what are the capability and permission boundaries?
- Filling: write the role in one sentence and make it able to determine what follows; write boundaries only when removing them would change the result; checkable red lines belong to [Hard Constraints].
- Placeholders:
  ```
  [Identity]
  You are 〈executor role〉.
  Capability and permission boundaries: 〈available inputs, tools, knowledge scope; actions allowed and not allowed〉.
  ```

## [Goal]

- Required elements: completion state. This section answers: in what state is the world once it is done?
- Filling: write only 1 sentence and state the state, not the action; include no steps or format; must not replace the draft's object.
- Placeholders:
  ```
  [Goal]
  〈object〉 reaches 〈observable state〉.
  ```

## [Requirement Description]

- Required elements: input, scenario. This section answers: in what scenario and with what input is what needed?
- Filling: write only the scenario, the input, and the expectation, with steps belonging to [Task Details]; for the scenario state the user and the timing; for the input state the form, the language, and the quantity or length range.
- Placeholders:
  ```
  [Requirement Description]
  - Scenario: used by 〈user〉 at 〈timing〉.
  - Input: 〈form〉; 〈language〉; 〈quantity or length range〉.
  - Expectation: 〈what is needed〉.
  ```

## [Fact Baseline]

- Required elements: at least 1 confirmed fact, or an explicit "no confirmed facts". This section answers: what is true, what still needs verification, and what is unknown?
- Filling: use three blocks — confirmed, assumptions pending verification, unknown — and do not mix them; annotate confirmed items with their source or with [User confirmed]; write assumptions pending verification with a default value and [Assumption]; mark unknown items with [Unknown]; must not fabricate version numbers, data, or tool capabilities.
- Placeholders:
  ```
  [Fact Baseline]
  Confirmed (must not be changed):
  - 〈fact〉 (source: draft)
  Assumptions pending verification (adopted by default; if reality differs, reality wins):
  - 〈assumption〉, default value: 〈default value〉 [Assumption]
  Unknown:
  - [Unknown] 〈unknown item〉
  ```

## [Task Details]

- Required elements: step sequence. This section answers: how is it done?
- Filling: each step = verb + object + completion marker, numbered in order; every input a step needs can be found in [Requirement Description] or [Fact Baseline]; a completion marker can be judged on its own; constraints belong to [Hard Constraints].
- Placeholders:
  ```
  [Task Details]
  1. 〈verb〉〈object〉. Completion marker: 〈checkable state〉.
  2. 〈verb〉〈object〉. Completion marker: 〈checkable state〉.
  ```

## [Hard Constraints]

- Required elements: at least 1 constraint with a check. This section answers: which lines must not be crossed?
- Filling: each item starts with MUST or MUST NOT followed by "Check:"; the check is limited to quantity, format, presence/absence, or reproducible steps; constraints come from the draft or carry [Assumption]; no words from references/vague-words.md; write no steps. Exactly 1 item locks the output language: it starts with MUST, names exactly 1 language — the language used to invoke the skill, so a Chinese invocation fixes 中文, overridden by a value the user explicitly specifies — and carries a "Check:".
- Placeholders:
  ```
  [Hard Constraints]
  - MUST: 〈what must be done〉. Check: 〈quantity / format / presence-absence / reproducible steps〉.
  - MUST: write the body in 〈output language〉; keep any span quoted from the user's original words in its original characters with an English gloss. Check: exactly 1 language name appears in this item, and the body uses no other language outside quoted originals.
  - MUST NOT: 〈what must not appear〉. Check: 〈quantity / format / presence-absence / reproducible steps〉.
  ```

## [Output Deliverables]

- Required elements: format, acceptance criteria. This section answers: what is delivered?
- Filling: list the deliverable, format, location, and acceptance criteria in a table, one deliverable per row; for the location state either inside the conversation reply or a file path; make the acceptance criteria judgeable one by one, expressed as quantity, format, presence/absence, or reproducible steps.
- Placeholders:
  ```
  [Output Deliverables]
  | Deliverable | Format | Location | Acceptance criteria |
  |---|---|---|---|
  | 〈name〉 | 〈format〉 | 〈location〉 | 〈judgeable criterion〉 |
  ```
