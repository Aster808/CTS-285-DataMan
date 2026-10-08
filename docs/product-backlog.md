# DataMan Product Backlog

## Sources

This backlog uses the validated requirements and the decisions recorded in these repository files:

* `docs/requirements.md`
* `docs/decisions/m3-backlog-triage-record.md`
* `docs/decisions/m3-product-owner-decision-record.md`

The requirements register was used as the source of truth for requirement IDs and validated needs. The triage record informed readiness, effort, dependencies, risk, and priority. The Product Owner simulation reinforced the importance of limited capacity, meaningful tradeoffs, and deferring work whose data or rules are not settled.

## Priority Order

1. US-01 — Immediate Answer Feedback
2. US-02 — Retry Incorrect Answers
3. US-03 — Support Identified Device Categories
4. US-04 — Save Learner Progress
5. US-05 — Resume Progress Across Devices
6. US-06 — View Learner Progress

## Stories

### US-01 — Immediate Answer Feedback

**Requirement ID:** FR-01, NFR-02

**User Story:** As a student practicing mathematics, I want to submit an answer and immediately see whether it is correct or incorrect so that I can understand my results and continue practicing.

**Acceptance Criteria:**

* Given that a student has entered a math problem and an answer, when the student submits the answer, then the application indicates whether the answer is correct or incorrect.
* Given that a student submits an answer, when the answer is checked, then correctness feedback is displayed without requiring the student to submit the answer again.
* Given that the student uses a supported device category, when the student submits an answer, then the answer-checking interaction remains usable on that device.

**Relative Effort:** S — This is a small, focused behavior compared with progress saving, learner identification, and cross-device continuation.

**Dependency / Constraint:** No prerequisite was identified for the basic answer-feedback behavior. The measurable response-time limit remains unresolved under Q-03.

**Priority:** 1

**Readiness:** Move Forward

**Priority Rationale:** This story preserves the core Answer Checker behavior and addresses a high-value learner need. The M3 triage record classified immediate feedback as high value, small effort, and low risk. The instructor stakeholder also identified it as required for the first usable release, making it the strongest first priority.

---

### US-02 — Retry Incorrect Answers

**Requirement ID:** FR-02

**User Story:** As a student practicing mathematics, I want to see the correct result after two incorrect attempts so that I can learn from my mistakes and continue practicing.

**Acceptance Criteria:**

* Given that a student has submitted an incorrect answer once, when the student submits another incorrect answer for the same problem, then the application displays the problem with its correct result.
* Given that a student has submitted an incorrect answer, when the student submits a correct answer on the next attempt, then the application does not incorrectly treat that answer as a second incorrect attempt.

**Relative Effort:** S — This is a small behavior that builds on the answer-checking flow rather than requiring the broader progress-saving work.

**Dependency / Constraint:** The answer-checking flow from US-01 must be available.

**Priority:** 2

**Readiness:** Move Forward

**Priority Rationale:** This story preserves behavior documented in the DataMan manual and provides direct learning value. The M3 triage record classified retry after an incorrect response as high value, small effort, and low risk. It follows immediate feedback because it depends on the answer-checking flow.

---

### US-03 — Support Identified Device Categories

**Requirement ID:** NFR-01

**User Story:** As a student who may use different devices at school or at home, I want DataMan to support the identified device categories so that I can practice mathematics using an available device.

**Acceptance Criteria:**

* Given a supported Chromebook, when a student uses the application's core math-practice workflow, then the workflow can be completed.
* Given a supported phone, when a student uses the application's core math-practice workflow, then the workflow can be completed.
* Given a supported tablet, when a student uses the application's core math-practice workflow, then the workflow can be completed.
* Given a supported home computer, when a student uses the application's core math-practice workflow, then the workflow can be completed.

**Relative Effort:** M — Supporting several device categories requires broader validation than a single focused answer-checking behavior.

**Dependency / Constraint:** The officially supported device models and browser versions must be clarified under Q-02. The requirement identifies device categories but does not establish a specific model or browser-version list.

**Priority:** 3

**Readiness:** Refine

**Priority Rationale:** Device support addresses the documented need for students to use school and home devices. It is important to the product's usability, but exact supported models and browser versions remain unresolved. Refinement is appropriate before the team treats device coverage as fully testable.

---

### US-04 — Save Learner Progress

**Requirement ID:** FR-03

**User Story:** As a student whose practice session may be interrupted, I want my game progress saved so that I can resume without re-entering previously saved work.

**Acceptance Criteria:**

* Given that a student has completed work that the application has saved, when the student's session is interrupted, then the saved progress remains available for recovery.
* Given that a student returns after an interruption, when the student resumes the session using the established recovery process, then previously saved work is restored without requiring it to be entered again.
* Given that the student has made progress after an earlier save, when the application saves the newer progress, then a later recovery does not replace it with older saved work.

**Relative Effort:** L — Progress persistence and recovery are larger than the basic answer-checking stories and involve unresolved session and saving decisions.

**Dependency / Constraint:** The learner identification and session approach must be clarified. The required save frequency remains unresolved under Q-08; a 30-second interval is not a validated requirement.

**Priority:** 4

**Readiness:** Refine

**Priority Rationale:** Preserving progress has high learner value, but the M3 triage record classified it as large effort with a medium risk and an identity/session dependency. The Product Owner simulation also reinforced that high-value work is not automatically ready to move forward. Refinement is necessary before the team commits to a specific recovery and saving approach.

---

### US-05 — Resume Progress Across Devices

**Requirement ID:** FR-04, FR-05, NFR-03

**User Story:** As a student who uses more than one supported device, I want to identify myself and resume my own saved progress on another device so that I can continue practicing without losing my work or accessing another learner's progress.

**Acceptance Criteria:**

* Given that a student's progress has been saved and the student has been identified, when the student resumes on another supported device, then the application retrieves the progress associated with that student.
* Given that two learners have different saved progress, when one learner identifies themselves, then the application does not display the other learner's saved progress.
* Given that a learner cannot be identified successfully, when the learner attempts to access saved progress, then the application does not grant access to another learner's progress.

**Relative Effort:** L — Cross-device continuation combines learner identification, saved-progress retrieval, and access restrictions, making it larger than the core practice stories.

**Dependency / Constraint:** US-04 and a defined learner-identification/session approach must be established. Authentication and privacy constraints remain unresolved under Q-01 and Q-05.

**Priority:** 5

**Readiness:** Refine

**Priority Rationale:** Cross-device continuation supports an established stakeholder need, and protecting each learner's progress is essential. However, this story depends on saving progress and resolving identity and privacy questions. Its large effort and unresolved dependencies make refinement more defensible than immediate implementation.

---

### US-06 — View Learner Progress

**Requirement ID:** FR-06

**User Story:** As a parent or teacher, I want to view a learner's current learning progress so that I can understand how the learner is progressing during mathematics practice.

**Acceptance Criteria:**

* Given that a learner has recorded learning activity, when a parent or teacher uses the agreed progress-viewing capability, then the application displays available information about that learner's current progress.
* Given that no progress information is available for a learner, when a parent or teacher requests the progress view, then the application indicates that progress information is not yet available rather than displaying invented results.

**Relative Effort:** M — Providing a basic progress view is a medium-sized item because it depends on available activity data and an agreed definition of the information to show.

**Dependency / Constraint:** Activity data must be available. The intended presentation and whether a separate dashboard or report is needed remain unresolved under Q-06. Access and privacy rules also need clarification under Q-05.

**Priority:** 6

**Readiness:** Refine

**Priority Rationale:** This story supports the parent/teacher stakeholder identified in the requirements register. The M3 triage record classified the activity summary as medium value, medium effort, and medium risk, with an activity-data dependency. It remains below core learner-practice and recovery work until the reporting need and available data are clarified.

## Open Questions Carried Forward

* **Q-01:** What authentication or user-identification method should support cross-device continuation? US-05 depends on this decision.
* **Q-02:** Which device models and browser versions must be officially supported? US-03 needs this information for complete acceptance testing.
* **Q-03:** What measurable response-time limit should define "immediately" for correctness feedback? US-01 must not assume an unsupported time limit.
* **Q-04:** What does "simple" mean in measurable terms for the modernized user interface? No decorative theme-selector story is included because a required theme has not been validated.
* **Q-05:** What student data may be stored, and what privacy or security constraints apply? This affects US-04, US-05, and US-06.
* **Q-06:** Is direct parent or teacher visibility sufficient, or is a separate dashboard or report needed? US-06 should not expand into an advanced analytics dashboard without validated need.
* **Q-07:** Which database technology, if any, should the development team select? No database technology is specified as a requirement, so no database-specific story or solution assumption is added.
* **Q-08:** How frequently must progress be saved to meet the need for session recovery? US-04 must not treat the previously suggested 30-second interval as validated.

## Revisions After Triage and Release Planning

* **US-01 — Confirmed first priority:** Kept immediate answer feedback at the top because the triage record identifies it as high value, small effort, and low risk, and the stakeholder requires it for the first usable release.
* **US-02 — Kept ready to move forward:** Preserved retry behavior as a focused story that depends on the answer-checking flow.
* **US-03 — Clarified readiness:** Identified supported device models and browser versions as unresolved constraints rather than assuming every device is supported.
* **US-04 and US-05 — Made dependencies visible:** Kept progress saving and cross-device continuation separate so the team can evaluate their distinct work. Both remain in refinement because identity/session decisions and saving details are unsettled.
* **US-06 — Limited scope:** Kept the validated need to view current learner progress but did not assume an advanced analytics dashboard or a particular reporting design.
* **Decorative theme selector — Deferred from the backlog:** No validated requirement establishes a theme selector as necessary. The unresolved meaning of "simple" remains an open question.
* **Product Owner release-planning lesson — Applied:** The StudyTrack simulation showed that limited capacity, critical dependencies, and unsettled data or rules should affect readiness and deferral decisions. Its StudyTrack story IDs and estimates were not copied into DataMan because they belong to a different product scenario.

The priority order favors core math-practice behavior first, then device support, progress recovery, cross-device access, and stakeholder reporting. The order can be revisited when the open questions are resolved or new evidence changes value, risk, effort, or dependencies.
