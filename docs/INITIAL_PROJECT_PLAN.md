# Crown Chase — Initial Project Plan

Status: **Initial / G1 proposal**, version 0.2, prepared November 16, 2026. No prototype work, agent setup, evaluation, or gate approval is claimed.

Accountable Owner: Scarlett Leon, Producer / Executive Producer and Creative Director. Scarlett retains every task's human ownership, reviews decisions and implementations, evaluates results, and integrates accepted work. The instructor is Gate Approver; peers supply Braintrust feedback and playtest observations.

## 1. Objective, sources, and commitment

Develop a one-world 2D fantasy platformer in which a princess overcomes enemies and obstacles on a quest to reclaim her magical crown from an evil witch. Investigate whether bounded AI-generated layouts adapted to performance provide more appropriate challenge and encourage continued play compared with predetermined fixed levels.

Requirements come from the local course reader v2.1, especially Sections 3.1–3.5, 5.2, 5.4–5.6, 5.8–5.9 and the G1–G3 playbooks. Design decisions come from Scarlett's 13-slide `docs/Crown_Chase.pdf`. The project brief supplements those decisions. The reader is a local, ignored reference and must not be published. Companion artifacts: [Initial GDD](INITIAL_GDD.md) and [Initial Configuration](INITIAL_CONFIGURATION.md).

**G1 decision requested (slide 13):** Approve prototype work: one playable environment; movement, enemies and obstacles; bounded AI generation; a fixed scripted baseline; and comparative playtests. Approval is not recorded in this repository. If placed on Hold, clarify generation feasibility, reduce generation complexity and the enemy/obstacle set, and demonstrate one valid generated level before proceeding.

## 2. Gates, dates, and artifact lifecycle

**Confirmed G1 assignment deadline: November 15, 2026, at 11:59 PM ET (Eastern Time)**, confirmed by Scarlett. This deadline has passed as of this document's November 16 preparation date. It is an assignment deadline, not the date or evidence of an instructor approval decision. G1 submission, acceptance, and approval are not claimed.

[OPEN P1] **G2, G3, G4, G5, and Alpha/Beta/Gold dates remain unconfirmed.** The local reader supplies no official gate deadlines and defers dates/submission details to the [published syllabus](https://courseworks2.columbia.edu/courses/258228/assignments/syllabus). Its November 9 pitch-round date is not a G1 deadline. The linked CourseWorks syllabus was inaccessible during the initial review; Scarlett's confirmation supplies the G1 deadline. Verify future dates and remaining submission details against the current syllabus rather than infer them from today's date, reader revision, or example timeline.

| Gate | Decision and required evidence from the reader | Proposed project evidence and next commitment |
|---|---|---|
| G1 Concept — assignment deadline **November 15, 2026, at 11:59 PM ET** (confirmed by Scarlett; approval decision separate) | Clear, achievable concept; pitch and required recording; X/player/motivation/loop/pillars; references; systems diagram; hypothesis/baseline/playtest question; budgets; six-dimension Risk Profile and mitigations; Initial GDD/configuration/plan/Risk Register | Proposal PDF plus these three documents, initial risk table below, and recording/submission details still to verify. Instructor approval authorizes only the agreed prototype investigation. G1 decision/conditions are recorded on CourseWorks. |
| G2 Prototype — date [OPEN P1] | First playable **with agent**, recording, Initial Playtest Log, Update GDD/configuration/plan/Risk Register, deterministic checks and budgeted live evaluation; observe at least one external player using the core loop for the combined review | Demonstrate movement/lives/power-ups, one-world layouts, bounded adaptive agent, fixed baseline, validation/fallback and traces. Record failed/unavailable runs and limits. Approval supports refinement and production planning; a successful API call is insufficient. |
| G3 Production — date [OPEN P1]; shares G2 review | Separate feasibility decision: scope lock, exclusions, Final Project Plan, updated Risk Register and GDD/configuration, prototype evidence, role coverage/capacity and release approach | Reconcile demonstrated behavior with remaining capacity; approve smaller content if needed; define Alpha/Beta/Gold checks and buffers. Instructor approval establishes production baseline. GDD/configuration remain Update. |
| G4 Final / Pre-Launch — date [OPEN P1] | Identified Gold candidate and recording; Final GDD/configuration; harness/results; updated Playtest Log/Risk Register; release instructions; verified fixes, accepted defects and full role coverage | Release only the approved build. Preserve tag; later corrective releases need recorded patches/tests and instructor approval. |
| G5 Retrospective / Closure — date [OPEN P1] | Final game/AAR, Final Playtest Log, project archive and syllabus showcase evidence; no additional G5 recording | Archive evidence and agent handoffs; play three assigned classmates' builds; follow draft-sharing/Braintrust schedule. Finals retrospective/capstone requirements remain separate syllabus items. |

The Project Plan is **Initial at G1**, **Update at G2**, **Final at G3 scope lock**; later changes reference the accepted baseline. GDD/configuration are **Initial at G1**, **Update at G2/G3**, **Final at G4**.

Alpha means all agreed features are implemented/integrated with gaps recorded. Beta means planned release content is complete/locked and work focuses on verification/polish/fixes. Gold is the identified release candidate meeting criteria and approved at G4. These are Production milestones, not extra gates. Proposed criteria: Alpha exercises platforming, agent/baseline and failure paths; Beta locks one-world content; Gold passes agreed deterministic checks, budget/fallback review and external release playtest with blocking defects resolved. [OPEN P2] Exact release thresholds and time/capacity allocation require approval at G3.

## 3. Work through G2 and dependencies

Sequence is relative to gate approval, not an invented calendar. [OPEN P2] Effort bands below are preliminary planning judgments (S = bounded document/fixture task, M = subsystem task, L = integration/testing task), not hours or validated capacity. Scarlett must supply available hours and estimates before scope lock, including player recruitment, fixes, reruns, recording and review buffers. Every row is **planned / not started**, except T1's current documentation draft.

| ID / task and outcome | Human Owner / proposed delegated role | Dependencies | Estimate | Acceptance and deliverable evidence |
|---|---|---|---|---|
| T1 Prepare/review G1 package | Scarlett / Design Lead, Producer, Tech Lead | Read sources | M | These documents preserve slide decisions, label open questions and budgets, and include risks/role map; Scarlett reviews draft. Recording, pitch submission and feedback evidence remain to complete. |
| T2 Confirm dates, gate conditions and capacity | Scarlett / Producer | T1; current syllabus | S | Record official dates/submission details, instructor decision and capacity; resolve P1/P2. Do not begin work conditional on G1 approval without that decision. |
| T3 Establish toolchain and minimal runnable project | Scarlett / Gameplay Programming, Publishing and Release | T2 and approval; C1/D1 | M | Another person can run the identified empty/minimal Godot project using setup instructions; version/export target selected. |
| T4 Implement core fixed-level loop | Scarlett / Gameplay Programming, Design Lead, Art/Narrative/Audio | T3; D2/D4/D5/D6 rules | L | One rough fixed level supports move/jump/stomp, enemies/obstacles, power-ups, life loss, retry, completion and Game Over; rules/feedback and edge cases reviewed. Preserve fixed baseline placements. |
| T5 Configure production assistants and extension | Scarlett / Tech Lead, Producer, QA | T2; C6/C9, syllabus manifest | M | Record all Section 5.2 role fields; configure a runnable extension with exact required manifest; demonstrate a bounded handoff and human review. May overlap T3/T4 after dependencies are known. |
| T6 Specify layout/state contract and fixtures | Scarlett / AI Integration, Design Lead | T4's movement parameters; D3/D7, C3 | M | Approved bounded context and schema, allowed catalog/difficulty bands, fixed/fallback fixtures, versioned physics; no agent authority over rules. |
| T7 Implement validator and fallback path | Scarlett / Testing and Validation, AI Integration | T6 | L | Reject malformed/disallowed/unsafe/impossible fixtures; accept known valid fixtures under movement rules; document traversability limits and validate fallback. |
| T8 Confirm supported model and private access | Scarlett / AI Integration | T2; C2/C8 | M | Resolve retirement conflict, approve replacement if needed, region/authentication/settings/price/token cap; no secrets in repo/client; budgeted access test recorded, including failure if unavailable. Can proceed independently of T7 once contract needs are understood. |
| T9 Integrate bounded live generation | Scarlett / AI Integration, Gameplay Programming | T6/T7/T8 | L | Performance summary → proposal → validation → level activation between sessions; total wait capped at 5 seconds; bounded retries/count/spending and late-response handling; fallback shown on forced failure. |
| T10 Run harness and baseline comparison checks | Scarlett / Testing and Validation | T4/T5/T7/T9 | L | Runnable deterministic commands/CI, bounded live evaluation, reproducible traces including failures, latency and actual spend; fixed mode never adapts; fallback runs labeled. |
| T11 Observe external player and collect Initial Playtest Log | Scarlett / Evaluation and Analysis, Design Lead, QA | T10; E1 consent/protocol; playable packaging | M | At least one external player uses core loop before combined G2/G3; record consent/anonymous ID, build/config, observations, ratings, retries and uncertainty; compare adaptive/fixed under approved procedure. No invented results. |
| T12 Revise and assemble G2/G3 evidence | Scarlett / Producer, all roles | T10/T11 | L | Triage findings, make feasible changes and verify them; Update GDD/configuration/plan/Risk Register; first playable/recording, log and evaluation evidence; propose separate G2 continuation and G3 scope-lock decisions. |

Critical path: rules/toolchain → fixed loop and movement parameters → contract → validator/fallback → live integration → checks → player observation → gate evidence. Model access can proceed in parallel with offline validation; access failure must be visible early. No unvalidated cloud success substitutes for a playable core loop. Role configuration and evidence must not be deferred until release.

## 4. Ownership, production role coverage, and coordination

The requested development-assistant functions map to course responsibilities:

| Requested assistance | GDF responsibility / handoff |
|---|---|
| Game Design and Documentation | Design Lead drafts rules and keeps documents consistent; hands specifications/test questions to Tech Lead/QA. |
| Gameplay Programming | Tech Lead implements movement, enemies, collision and platforming; hands build and cases to QA. |
| AI Integration | Tech Lead implements bounded generation/Vertex contract; hands traces, versions and failure cases to QA. |
| Testing and Validation | QA tests gameplay/generated layouts, reproduces failures and independently verifies fixes. |
| Evaluation and Analysis | BI organizes anonymous measurements/observations and limits; informs Design Lead and Scarlett's decisions. |

Additional course coverage: Producer handles plans, risks and PPP; Art Lead handles readability/assets; Narrative handles minimal story/copy; Audio handles bounded cue work; Publishing and Release handles runnable packaging, instructions and archive. The [Configuration role table](INITIAL_CONFIGURATION.md#8-production-assistants-and-role-coverage) records proposed executable artifacts, purpose, context, permissions, outputs, recipients/handoffs, evaluation and approval for each role. These are proposed roles, not configured assistants. No subagents were configured as part of this documentation task.

Scarlett is the accountable Owner across all roles and retains decisions, code review, result interpretation and integration. The in-game agent only proposes level data; it is not a producer, designer or developer with repository authority. Instructor gate approval remains separate from Scarlett's review.

**After G1, move coordination to Asana; it must be in use from G2.** Create tasks with student Owner and delegated GDF role, acceptance criteria, dependencies, estimates, evidence links and risks. Maintain weekly **PPP: Progress / Plans / Problems** with observed outcomes, next outcomes and blockers/decisions. Record instructor decisions from G2 onward in the gate task with reviewed versions, approved scope/build, conditions and follow-up. Use GitHub for code/PR/CI/release evidence and CourseWorks for submissions/private feedback. [OPEN P3] Asana project location, actual role configurations and work-cycle cadence are undecided. No Asana changes are made by this plan.

## 5. Initial Risk Profile and Risk Register

Original ratings and evidence below come from **slide 12**. They are qualitative concept evidence, not test results. All mitigations are planned; none is claimed complete. Scarlett owns each risk; delegated responsible roles and next checks are proposals. Separate likelihood/impact assessments need refinement at G2/G3 rather than pretending a dimension rating is a measured probability.

| Dimension / original rating | Risk and presentation evidence | Planned mitigation | Responsible role / detection and next check | Contingency / status |
|---|---|---|---|---|
| IP / Concept — **Medium** | Similarities and licensing requirements for borrowed code/assets. Evidence: inspiration from Super Mario. | Original assets where possible; verify licenses before reuse. | Art Lead / Design Lead; review provenance before any asset/code import (T4/T6). | Replace unapproved material with original/approved placeholders; reuse requires Scarlett approval. Open; impact/likelihood refinement at G2. |
| Business / Audience — **Medium** | Adaptive mechanic may not engage players. Evidence: established classic-platformer audience, but Crown Chase has not been playtested. | Conduct playtests and gather feedback. | BI / Design Lead; T11 voluntary retry, enjoyment, challenge and continuation observations. | Revise difficulty policy and simplify layouts; preserve comparative evaluation even if hypothesis is unsupported. Open; no audience validation. |
| Technology — **High** | Generated levels may be impossible, unfair or slow. Evidence: generation must satisfy movement, collision and difficulty constraints. | Deterministic validation and predefined fallback levels. | Tech Lead / QA; T7 invalid/valid fixtures and T9/T10 latency/failure evidence. Current model retirement is additional external evidence, not slide evidence. | Use fallback for failed requests; reduce generation complexity to constrained patterns if approved. Resolve model access before live integration; escalate gate feasibility if no agent works. Open. |
| Team — **Medium** | Development/integration may exceed capacity. Evidence: game development, agent integration, testing and documentation all required. | Define roles, review AI-generated code and prioritize core features. | Producer; T5 bounded handoff and review workload/capacity check before G2/G3. | Combine roles, shorten tasks and cut optional content; Scarlett keeps review/integration authority. Open; capacity unmeasured. |
| Genre / Mechanics — **Medium** | Poor movement/difficulty balance may frustrate players. Evidence: platforming depends on responsive controls and predictable hazards. | Test movement and obstacle difficulty before expanding variety. | Design Lead / QA; T4 controls/edge cases and T11 external player evidence. | Simplify hazards/enemies and retune approved physics, then revalidate affected layouts. Open; fairness untested. |
| Timeline — **High** | Full platformer plus adaptive generation may exceed time. Evidence: original concept includes multiple worlds, enemies and an AI system. | One-world prototype; prioritize agent comparison. | Producer; review T6–T12 critical path, dates and capacity at T2 and before scope lock. | Cut extra enemies, extra obstacles and decoration; preserve loop/evaluation; seek instructor review for commitment changes. Open; G1 assignment deadline confirmed, future calendar unverified. |

This table is the usable **Initial Risk Register** embedded in the G1 plan, with risk, evidence, responsible role, mitigation, contingency and next check. At G2/G3, develop the fuller Asana register with explicit likelihood and impact reasons, individual triggers/dates, status, residual risk, task/evidence links and next review. Update through G4 and archive at G5.

## 6. Scope, budgets, and reduction triggers

Included: one playable fantasy world, movement/jumping, simple enemies/obstacles, power-ups/lives, adaptive layouts, deterministic validation/fallback, fixed scripted baseline, basic playtest tracking. Excluded: multiple completed worlds, complex bosses, multiplayer, extensive inventory, full storyline/ending and large enemy roster. (Slide 10.)

Cut additional enemy varieties, extra obstacles and decorative content first. Proposed trigger: if T4 movement or T7 validation cannot support the content set before integration, freeze optional content and use the smallest approved catalog. If T9 cannot meet time/cost or validity constraints, simplify generation within approved bounds and demonstrate a valid level; use fallback during failures while preserving the working agent requirement and honest evaluation. Any material change to an approved gate commitment goes to the instructor; no automatic scope downgrade is authorized.

Preserve core platforming and agent-versus-baseline evaluation. A complete narrative ending is not required by the prototype; define a clear prototype completion state (D6) without adding a full campaign.

Slide 11 budgets: generate between gameplay sessions, 2–3-second target, 5-second maximum wait/fallback, less than $0.01 model spending target/session, $0.05 maximum, estimated 6 requests/session and provisional $0.0036/session. The brief proposes making six a maximum including retries. The $0.0036 figure uses original Gemini 2.5 Flash-Lite assumptions and is not a verified replacement-model estimate. Google Cloud Vertex AI remains the proposed platform; **Gemini 3.5 Flash-Lite is the proposed replacement**, not configured, tested, or approved. Configuration Section 7 cites official lifecycle/pricing sources and separately calculates $0.0186/session under standard global pricing with the same token/request assumptions. That estimate exceeds the unchanged less-than-$0.01 target but remains below $0.05. No budget or latency target is experimentally validated; the 5-second fallback requirement remains. [OPEN C2] Approve model use/configuration, confirm project/region access, and address the target gap. [OPEN D3/C7/P2] Session definition, enforcement and total development/evaluation/cloud budgets remain unapproved.

## 7. Evaluation, gate evidence, and four critical questions

G2 tests the hypothesis against predetermined nonadaptive levels using completion rate, retries, difficulty/enjoyment ratings and willingness to continue. Observe voluntary retries and record coaching, failures, fallbacks, configuration, latency/cost and uncertainty. Keep gameplay rules/catalog comparable. Protocol and success thresholds remain E1. One external G2 participant provides preliminary evidence only.

Reserve post-G2/G3 time for a revised encounter playtest linked to a finding/change, at least two distinct external players across G2–G4, and an external release playtest after Alpha/before Gold recording. The Initial Playtest Log starts at G2, updates at G4 and becomes Final at G5. The harness needs deterministic invariants and budgeted live runs, including unavailable/failed runs. No playtests or live trials have occurred here.

At each gate, organize evidence around:

- **Opportunity:** Classic platforming mastery and fantasy progression for the stated audience; adaptation's benefit remains a hypothesis.
- **Execution:** At G1, proposed architecture, work sequence and budgets; at G2, first playable and actual test evidence; at G3, feasible remaining production and release checks.
- **Risks and Mitigations:** Six dimensions above, observed triggers, failed assumptions, contingencies and owners.
- **Alignment:** GDD rules match configuration boundaries, implementation evidence, budgets and the plan's approved scope. Record contradictions and changes rather than retroactively rewriting observations.

Record gate/date/build/configuration, requested decision, changes since prior review, demonstration/evidence, exclusions, next commitment and artifact links. The instructor's actual decision must remain distinct from a student proposal.

## 8. Complete open-question register and approval needs

Every unresolved item in these three documents maps to this register. References such as “date P1” or “C4” reuse the same item rather than introduce a new decision.

| ID | [OPEN] question / decision | Scarlett's responsible role / needed checkpoint |
|---|---|---|
| D1 | Which target platforms/export format, devices, bindings, pause/menu and remapping controls? | Design Lead / before toolchain and input implementation |
| D2 | Which world theme, art/readability/accessibility approach, minimum narrative, audio and asset pipeline? | Design Lead, Art/Narrative/Audio / before content expansion |
| D3 | What is a player session for budgets/generation, when do transitions occur, and does retry retain a layout? | Design Lead / before accounting and integration |
| D4 | Which predefined enemy/obstacle types, behaviors, stomp/damage interactions and parameters? | Design Lead / before catalog freeze |
| D5 | Starting lives, health, power-up effects/duration, invulnerability, death triggers, damage and reset rules? | Design Lead / before fixed-loop acceptance |
| D6 | Completion trigger, prototype end state, levels/length, checkpoints, scoring or no scoring, simultaneous event priority? | Design Lead / before fixed-loop acceptance |
| D7 | Which performance-to-difficulty policy, allowed bands and fairness limits? | Design Lead / before adaptive comparison |
| C1 | Godot version/language, editor/runtime/export tooling, packages/versions and reproducible setup? | Tech Lead / before runnable project |
| C2 | Approve proposed Gemini 3.5 Flash-Lite (`gemini-3.5-flash-lite`) on Vertex AI; confirm project/region access, settings/output limits and measured latency/cost, and address the $0.0186 estimate exceeding the unchanged less-than-$0.01 target? | Tech Lead / before paid/live use |
| C3 | Which world-state/layout schema, coordinates, IDs, versioning and serialization format? | Tech Lead / before validator/loader implementation |
| C4 | Which traversability algorithm and limits, spawn/geometry checks, fallback catalog/selection and invalid-fallback recovery? | Tech Lead / QA / before level activation |
| C5 | Which memory window/reset/persistence, log storage/access, retention/deletion, anonymity and public evidence policy? | Tech Lead / BI / before collecting data |
| C6 | Which reviewed prompts, settings, refusal format and native configurations for each development role and in-game agent? | Tech Lead / before delegated execution/live trials |
| C7 | Exact regeneration/retry limits, token caps, backoff and conservative pending-cost reservation/count enforcement within 5 seconds, 6 requests and $0.05/session? | Tech Lead / before claiming budget enforcement |
| C8 | Local adapter or trusted backend, hosting/authentication/IAM/quota controls and non-model infrastructure costs? | Tech Lead / before integration/deployment |
| C9 | Which runnable agent extension and common manifest, with what exact syllabus fields and demonstration of all role coverage? | Tech Lead / before role evidence acceptance |
| C10 | Which harness/CI commands/paths, log format and sanitized trace/evidence pipeline? | QA / Tech Lead / before G2 evidence |
| E1 | Consent/recruitment/sample size, ratings, ordering/equal exposure, metric definitions and decision criteria? | Design Lead / BI / before external testing |
| R1 | Is any SuperTux Classic or other third-party reuse desired? If proposed, which exact files/licenses/attribution/distribution obligations? | Art Lead / Tech Lead / approval before copying |
| P1 | Official G2/G3/G4/G5 and Alpha/Beta/Gold dates, remaining pitch/recording/submission details, and showcase/Braintrust/Finals requirements? G1 assignment deadline is confirmed as November 15, 2026, at 11:59 PM ET; submission/acceptance/approval are not claimed. | Producer / verify current syllabus before gate submission |
| P2 | Available hours, task estimates, total development/evaluation budget, buffer and exact release acceptance thresholds? | Producer / before Final G3 baseline |
| P3 | Asana project, work-cycle cadence, concrete delegated ownership/handoffs and access boundaries? | Producer / after G1, operational by G2 |

Approval-sensitive assumptions: Godot remains proposed; schemas/validator/broker/prompt paths and role configurations are candidates; six as a hard request cap and a single total deadline are proposed interpretations of the brief; adaptation/evaluation policy and capacity estimates need review. Gemini 3.5 Flash-Lite is proposed only; model use/configuration, code/asset reuse, cloud spend and executable assistant setup are not approved by these documents. G1’s assignment deadline is confirmed; future milestone dates remain [OPEN P1].

## 9. Final documentation verification and remaining requirements

Checked against reader Section 5.2 and relevant planning templates:

| Requirement | Coverage / current limitation |
|---|---|
| GDD player, genre/platform, loop, mechanics/dynamics/aesthetics, progression/scoring, outcomes/edge cases/balance, controls/feedback/content/references/questions | GDD Sections 2–9; unresolved specifics marked D1–D7 rather than invented. No implemented/verified behavior claimed. |
| Configuration purpose/context/tools/permissions/knowledge/memory/models/prompts/failures/evaluation/logging/override/limits/fallback/versioning/artifacts/tests/CI | Configuration Sections 1–10; candidates and absent paths/commands labeled. No working configuration claimed. |
| Production-role fields and executable extension | Full proposed role table and extension task T5; executable configurations, exact manifest fields and evidence of use are still missing implementation work. |
| Initial planning, six-risk profile/register, tasks/dependencies/ownership/PPP and gates | This plan Sections 2–7; fuller estimates/Asana register at G2/G3, Final plan at G3. G1 assignment deadline is confirmed; future dates remain [OPEN P1]. |
| G1/G2/G3 deliverables | Evidence matrix and tasks identify required pitch/recordings, first playable/agent, logs/harness, updated documents and scope lock; these future deliverables are not claimed complete. |

Compared all 13 presentation slides: story, motivation, loop, pillars, alternatives, Mario attribution, agent boundary/hypothesis/baseline, one-world scope/exclusions, all slide budgets, six risk ratings/evidence, and slide 13's decision/Hold path are retained. Differences/clarifications for review:

- The actual local PDF uses an underscore in its filename; all 13 slides were read.
- **Documented model revision:** Official Google documentation confirms the original Gemini 2.5 Flash-Lite retired on October 20, 2026, and supports Gemini 3.5 Flash-Lite as the proposed Vertex AI replacement. The historical slide choice/$0.0036 estimate are preserved; the separate revised estimate is $0.0186/session, with primary-source links in Configuration Section 7. Model approval/configuration and the target gap remain [OPEN C2].
- The brief adds Godot, SuperTux history, detailed metrics and token assumptions not stated on the slides; they are labeled supplemental/proposed.
- Slide 10 excludes the full storyline and ending and includes extra obstacles in first cuts; those details are retained alongside the brief's scope. The larger multi-world story is not a promise of multiple prototype worlds.
- Slide 11 estimates six requests; the brief proposes six as a maximum. The plan explicitly treats that cap and retry accounting as proposed configuration, not a measured result.

No unresolved design conflict between the two local sources was found: the reader supplies assignment requirements rather than a competing game design. Exact current syllabus requirements cannot be certified from the reader alone. Missing information includes future official dates, remaining submission details and exact manifest fields; Scarlett has confirmed the G1 assignment deadline as November 15, 2026, at 11:59 PM ET, without claiming submission, acceptance, or approval. Missing future evidence includes executable role coverage/extension, build, harness/CI, live budgets and playtests, Asana coordination and gate decisions. These gaps are visible and scheduled; this documentation task does not complete those later course deliverables.

Public-repository check: only these three planning documents and the requested `.gitignore` protection are created. No course-reader body, copied game code/assets, API keys, access tokens or private cloud configuration is included. `docs/gdf.md` is ignored and untracked. The proposal PDF remains an existing untracked local reference, and is not staged by this work; Scarlett should explicitly choose whether to publish it later. The existing `.DS_Store` is unrelated and unchanged. No files are staged, committed or pushed; the old `game-dev-f26` repository is unchanged.
