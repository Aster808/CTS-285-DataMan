# DataMan Requirements Register

## Project Context

The DataMan modernization project aims to provide students with a way to practice mathematics independently while allowing parents or teachers to observe learning progress. The project must preserve the core math-practice behavior while supporting students who may use different devices and experience interrupted sessions.

## Evidence Notes

* **E-01 — Source:** DataMan manual, *Answer Checker (Operating Notes)*
  **Evidence:** A learner enters a math problem and an answer. DataMan indicates whether the answer is correct or incorrect.

* **E-02 — Source:** DataMan manual, *Answer Checker (Operating Notes)*
  **Evidence:** After two incorrect attempts, DataMan displays the problem with the correct result. The manual also describes score tracking after ten problems.

* **E-03 — Source:** M2 Elicitation Decision Record
  **Evidence:** The primary learner is a student practicing independently, often with a teacher or parent nearby. Students and parents have different needs.

* **E-04 — Source:** M2 Elicitation Decision Record
  **Evidence:** Students may use school Chromebooks, phones, tablets, and home computers. The system cannot assume that students always use the same device.

* **E-05 — Source:** M2 Elicitation Decision Record
  **Evidence:** Some sessions may be interrupted before the student intentionally signs out. The decision record identifies cross-device continuation as a need.

* **E-06 — Source:** M2 Elicitation Decision Record
  **Evidence:** Cross-device continuation requires a way to identify the learner and associate saved progress with the correct profile.

* **E-07 — Source:** M2 Elicitation Decision Record
  **Evidence:** Stakeholders have not confirmed a required color scheme or visual theme, and the meaning of “simple” remains unresolved.

* **E-08 — Source:** M2 Elicitation Decision Record
  **Evidence:** The stakeholder expects the development team to choose the database technology. No specific database has been established as a requirement.

## Functional Requirements

### FR-01

**Requirement:** The application must allow a learner to enter a math problem and answer, then indicate whether the answer is correct or incorrect.

**Source/Rationale:** E-01 documents the original DataMan Answer Checker behavior. This preserves the core math-practice capability.

### FR-02

**Requirement:** After two incorrect attempts at a problem, the application must display the problem with its correct result.

**Source/Rationale:** E-02 documents this behavior in the original Answer Checker.

### FR-03

**Requirement:** The application must save a learner’s game progress so that the learner can resume an interrupted session without re-entering previously saved work.

**Source/Rationale:** E-05 establishes that sessions may be interrupted and that students need to continue their work.

### FR-04

**Requirement:** The application must allow a learner to resume a saved session after identifying themselves on another supported device.

**Source/Rationale:** E-04 and E-06 establish the need for cross-device continuation and learner identification.

### FR-05

**Requirement:** The application must associate saved game progress with the correct learner.

**Source/Rationale:** E-06 establishes that cross-device synchronization requires a way to identify the learner and retrieve the correct saved progress.

### FR-06

**Requirement:** The application must provide a way for a parent or teacher to view the learner’s current learning progress.

**Source/Rationale:** E-03 identifies parents and teachers as people who may be nearby while a student practices. The exact presentation of progress remains unresolved.

## Non-Functional Requirements

### NFR-01

**Requirement:** The application must support use on the device categories identified in the project evidence: Chromebooks, phones, tablets, and home computers.

**Source/Rationale:** E-04 identifies these device categories. The specific supported models and browser versions remain an open question.

### NFR-02

**Requirement:** The application must provide correctness feedback immediately after a learner submits an answer.

**Source/Rationale:** E-01 and E-02 describe the Answer Checker’s correctness feedback, including its immediate indication of an incorrect answer. The exact maximum response time still needs to be defined.

### NFR-03

**Requirement:** The application must restrict access to saved student progress so that a learner can access only the progress associated with their own identified profile.

**Source/Rationale:** E-06 establishes the need to associate saved progress with the correct learner. The authentication method and detailed privacy constraints remain unresolved.

## Open Questions / Assumptions

* **Q-01:** What authentication or user-identification method should support cross-device continuation?
* **Q-02:** Which device models and browser versions must be officially supported?
* **Q-03:** What measurable response-time limit should define “immediately” for correctness feedback?
* **Q-04:** What does “simple” mean in measurable terms for the modernized user interface?
* **Q-05:** What student data may be stored, and what privacy or security constraints apply?
* **Q-06:** Is direct parent or teacher visibility sufficient, or is a separate dashboard or report needed?
* **Q-07:** Which database technology, if any, should the development team select?
* **Q-08:** How frequently must progress be saved to meet the need for session recovery? The previous 30-second interval was not established by stakeholder evidence.
