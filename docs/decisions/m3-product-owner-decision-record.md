# M3 Product Owner Decision Record

## Scenario
StudyTrack release planning under constrained capacity.

## Round 1 — Capacity 13
- ST-01: Create a study task (3 pts)
- ST-02: Mark a study task complete (2 pts)
- ST-03: Recover a missed task (3 pts)
- ST-04: Keyboard-accessible task entry (2 pts)

**Why this release slice was defensible:**
My selected release slice is ST-01, ST-02, ST-03, and ST-04 for a total of 10 points out of 13. These features let students create tasks, track progress, recover missed tasks, and use keyboard navigation.

**One intentional deferral and why:**
I deferred ST-07 (AI study recommendations) because it needs more refinement, and the study-history data and recommendation rules are not yet settled.

## Complication
Capacity dropped from 13 to 10 points. Keyboard accessibility testing revealed that task entry cannot reliably be completed with keyboard navigation, so ST-04 became release-critical.

## Revised Release Slice — Capacity 10
- ST-01: Create a study task (3 pts)
- ST-02: Mark a study task complete (2 pts)
- ST-03: Recover a missed task (3 pts)
- ST-04: Keyboard-accessible task entry (2 pts)

### Removed after complication
- None

### Added after complication
- None

**What changed and why:**
My plan changed by removing ST-04 and adding ST-05, so the revised plan focuses more on basic planning, task completion, recovery, and progress tracking.

**Tradeoff accepted:**
I accepted the tradeoff of delaying keyboard-accessible task entry so the release could include the weekly progress summary within the limited capacity.

## Transfer to DataMan
Before finalizing your DataMan backlog, review whether any item is high value but not ready, depends on unresolved work, consumes disproportionate effort, or should move because it reduces risk or unlocks other work.
