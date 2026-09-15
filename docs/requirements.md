# DataMan Requirements Register

## Project Context

The DataMan modernization project is intended to provide a simple, modern learning experience for students practicing mathematics independently, while also allowing parents to verify learning progress. The system must support students who may use different devices and may have their sessions interrupted unexpectedly. The modernization effort therefore needs to balance simplicity with reliable progress continuation across supported devices.

## Evidence Notes

- **E-01 — Source:** M2 Elicitation Decision Record  
  **Evidence:** The primary learner is a student practicing independently, often with a teacher or parent nearby. The decision record identifies students and parents as distinct end-users with different needs.

- **E-02 — Source:** M2 Elicitation Decision Record  
  **Evidence:** Students may use DataMan on school Chromebooks, phones, tablets, and home computers. The system cannot assume that a learner will always use the same device.

- **E-03 — Source:** M2 Elicitation Decision Record  
  **Evidence:** Some student sessions may be interrupted before intentional sign-out. The decision record states that the original local-only session constraint is no longer defensible.

- **E-04 — Source:** M2 Elicitation Decision Record  
  **Evidence:** Cross-device continuation requires some form of unique user identification. The decision record concludes that a centralized user account system must be reconsidered because persistent user profiles are necessary for cross-device syncing.

- **E-05 — Source:** M2 Elicitation Decision Record  
  **Evidence:** Stakeholders have not established a specific color scheme or visual theme as a requirement. The meaning of "simple" also remains unresolved.

- **E-06 — Source:** M2 Elicitation Decision Record  
  **Evidence:** The stakeholder did not select a database technology and expected the development team to decide. Therefore, a specific database technology is not a confirmed user or business requirement.

## Functional Requirements

### FR-01

**Requirement:** The application must automatically save active game progress and ongoing session scores at least every 30 seconds so that interrupted sessions can be resumed.

**Source/Rationale:** E-02 and E-03 establish that students may change devices and experience interruptions. The revised elicitation decision identifies automatic saving every 30 seconds as the revised functional requirement.

### FR-02

**Requirement:** The application must allow a student to resume an interrupted game session after logging in from another supported device.

**Source/Rationale:** E-02 and E-04 establish the need for cross-device continuation and some form of unique user identification.

### FR-03

**Requirement:** The application must provide students with access to active mathematics learning activities and their current game progress during a practice session.

**Source/Rationale:** E-01 establishes that the primary learner is a student practicing independently. This requirement preserves the core learning purpose without prescribing a particular interface or technology.

### FR-04

**Requirement:** The application must identify a student's saved session or profile sufficiently to associate saved game progress with the correct learner.

**Source/Rationale:** E-04 establishes that cross-device synchronization requires some form of unique user identification. The specific authentication method remains an open question.

## Non-Functional Requirements

### NFR-01

**Requirement:** The web application must dynamically scale its user interface and maintain the core game loop across ChromeOS, iOS, Android, and Windows-supported environments.

**Source/Rationale:** E-02 identifies Chromebooks, phones, tablets, and home computers as possible devices. The revised elicitation decision explicitly identifies multi-platform interoperability as a non-functional requirement.

### NFR-02

**Requirement:** The application must preserve active game progress and session scores when a student experiences an accidental browser refresh or temporary network interruption, provided that previously saved progress is available.

**Source/Rationale:** E-03 establishes that sessions may be interrupted before intentional sign-out and that losing work is a concern.

### NFR-03

**Requirement:** The application must restrict access to saved student progress so that a student can only resume the session associated with their identified profile.

**Source/Rationale:** E-04 establishes that cross-device synchronization requires some form of unique user identification. The specific authentication method remains an open question.

## Open Questions / Assumptions

- **Q-01:** What specific authentication or user-identification method should be used to support cross-device session continuation?

- **Q-02:** What devices and browser versions will be officially supported?

- **Q-03:** What does "simple" mean in measurable terms for the modernized user interface?

- **Q-04:** What specific performance expectations should the application meet across supported platforms?

- **Q-05:** What student data may be stored in the centralized system, and what privacy or security constraints apply?

- **Q-06:** Is synchronous, over-the-shoulder parent visibility sufficient, or is a separate parent dashboard or asynchronous report actually needed?

- **Q-07:** Which database technology, if any, should the development team select? The stakeholder has not established a database preference.

## Final Quality Check

- [x] Clear enough for another team member to interpret consistently.
- [x] Supported by evidence, a stakeholder need, or a confirmed project constraint.
- [x] Testable or verifiable later.
- [x] Solution-neutral enough for this stage of the project.
- [x] Focused on one main capability or quality.
- [x] Classified correctly as functional or non-functional.

Also confirm:

- [x] At least four functional requirements are included.
- [x] At least three non-functional requirements are included.
- [x] Every confirmed requirement has a source/rationale.
- [x] Open questions and assumptions are separated from confirmed requirements.
- [ ] The simulation decision record is saved at `docs/decisions/m2-elicitation-decision-record.md`.
- [ ] This file is saved as `docs/requirements.md`, committed, and synced to GitHub.