# M2 Elicitation Decision Record

## Investigation Path
1. Who will use the system and in what setting?
   Evidence revealed: The primary learner is a student practicing independently, often with a teacher or parent nearby. Exact device and access conditions have not yet been confirmed.
2. What colors and visual theme should the new version use?
   Evidence revealed: Stakeholders have preferences, but no evidence shows that a specific color scheme is required for the system to meet the project need.
3. Which database technology should the team use?
   Evidence revealed: The stakeholder says, “I do not know. I expected the development team to decide that.” This does not establish a user or business requirement.

## Initial Position
**Supported evidence:**
Dual Target Audience: The requirements must account for two distinct end-users with different interfaces: the student (who interacts with active games) and the parent (who verifies learning progression).

**Remaining uncertainty:**
The Scope of "Simple": We lack metrics on what constitutes "simple" for a modern user interface. We do not know if stakeholders expect a skeuomorphic retro LED display aesthetic or a minimalist, modern educational layout.

**Likely functional requirement:**
Likely Functional Requirement (FR)FR-01 (Parent Visibility): The web application must provide a real-time, on-screen summary or overlay of active learning objectives and current score metrics during gameplay, allowing a supervising parent to instantly identify the mathematical concept and proficiency level of the child.

**Likely non-functional requirement / quality constraint:**
Likely Non-Functional Requirement (NFR)NFR-01 (Session Resilience): The application must preserve active game progress and ongoing session scores in the event of an accidental browser tab refresh or temporary local network drop, resuming the exact state upon reload without requiring data re-entry.4. Intentional Exclusions (Not Treated as Requirements)Excluded Solution: Creating an Asynchronous Parent Email Report Dashboard.Why: While an automated email digest or complex analytics portal solves the parent oversight issue, it is a heavy technical solution that may violate the mandate to "keep it simple." Until stakeholders confirm that synchronous, over-the-shoulder visibility is insufficient, this remains a proposed solution, not a requirement.5. Why This Position is DefensibleThis position is defensible because it avoids premature optimization and costly architectural commitments while completely satisfying the immediate stakeholder inputs. By anchoring the NFR to session stability rather than an immediate full-scale relational database infrastructure, we minimize initial development complexity while addressing the fear of "losing work."Furthermore, by grounding the parent requirement in UI clarity rather than a separate administrative portal, we honor the "keep it simple" constraint until further discovery proves a more complex solution is mandatory. Would you like to adjust the wording of either requirement, or should we move on to creating the stakeholder validation plan?AI can make mistakes, so double-check responses

**Assumption or proposed solution I am not treating as confirmed:**
Excluded Solution: Creating an Asynchronous Parent Email Report Dashboard.Why: While an automated email digest or complex analytics portal solves the parent oversight issue, it is a heavy technical solution that may violate the mandate to "keep it simple." Until stakeholders confirm that synchronous, over-the-shoulder visibility is insufficient, this remains a proposed solution, not a requirement.

**Why my initial position is defensible:**
This position is defensible because it avoids premature optimization and costly architectural commitments while completely satisfying the immediate stakeholder inputs. By anchoring the NFR to session stability rather than an immediate full-scale relational database infrastructure, we minimize initial development complexity while addressing the fear of "losing work."Furthermore, by grounding the parent requirement in UI clarity rather than a separate administrative portal, we honor the "keep it simple" constraint until further discovery proves a more complex solution is mandatory.

## Complication
Students may use DataMan on school Chromebooks, phones, tablets, and home computers. Some sessions may be interrupted before intentional sign-out.

**What this affects:**
Infrastructure & Security: We are forced to shift from a standalone, stateless client-side web app to a cloud-backed application architecture featuring persistent user state tracking. This also brings student data privacy and authentication constraints into play.

**What I revised, if anything:**
Our initial local-only session constraint is no longer defensible.Requirement TypeInitial PositionRevised PositionFunctional Requirement (FR-01)The app must provide a real-time on-screen summary for parents.FR-01 (Cross-Device Continuation): The application must automatically save active game progress to a cloud database every 30 seconds, allowing students to resume an interrupted session from any supported device upon logging back in.Non-Functional Requirement (NFR-01)The app must preserve progress locally via browser caching.NFR-01 (Multi-Platform Interoperability): The web application UI must dynamically scale and maintain core game loop performance across ChromeOS, iOS, Android, and Windows ecosystems.

**Final decision and reasoning:**
My final decision is to reopen the previously excluded assumption regarding a centralized user account system.Why This Decision is Defensible:We can no longer defer the "persistent user profiles" discussion. Cross-device syncing natively requires some form of unique user identification (e.g., a simple class code, a Google Student Sign-In for Chromebooks, or an anonymized student ID).While this adds complexity and challenges the stakeholder mandate to "keep it simple," it is the only way to satisfy the higher-priority user reality that students will change hardware mid-session and experience abrupt interruptions. Ignoring this now would result in critical architectural rework later in the development cycle.

## Next Project Action
Use this evidence to update the DataMan Requirements Register and preserve any unresolved questions as open assumptions or follow-up items.
