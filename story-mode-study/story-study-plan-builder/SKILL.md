---
name: story-study-plan-builder
description: Build a complete story-based certification study-plan package from an attached study guide and exam blueprint. Use when the user wants a reusable, episode-based, season-based, Socratic learning project with characters, setting, continuity, blueprint coverage, review modes, learner tracking, labs, and session output templates. Begin by interviewing the user in structured rounds, then inspect the source files, design the curriculum, generate all package files, validate coverage, and save the completed package to disk.
---
# Story-Based Study Plan Builder
## Purpose
Create a reusable story-mode study package from two primary inputs:
1. A vendor study guide or set of study guides
2. An official exam blueprint, course outline, or certification objectives document
The result must be more than a topic list. It must be a coherent learning system in which:
- The story creates a realistic operational requirement.
- The technical concept solves that requirement.
- The learner reasons before receiving the explanation.
- Evidence proves the answer.
- Sessions build on one another through persistent characters, topology, organisation, and learner-state tracking.
- The exam blueprint remains the curriculum authority.
This skill is intended for Claude Code in VS Code. It must read the source files in the current workspace, ask the user a structured series of questions, create the package as files, validate it, and report what was created.
---
# Non-Negotiable Behaviour
## Always interview before building
Do not immediately generate the study plan.
When this skill starts:
1. Locate likely study guides and blueprints in the workspace.
2. Briefly state which files appear to be the technical sources.
3. Begin the discovery interview below.
4. Ask questions in manageable rounds.
5. Wait for the user's answer after each round.
6. Summarise the decisions after the final round.
7. Ask for one final confirmation only if major ambiguity remains.
8. Then build the complete package without repeatedly asking for permission.
Do not ask one question at a time during the design interview unless the user requests that style. The interview is deliberately a structured questionnaire. Normal teaching sessions created by the package may still use one Socratic question at a time.
## Use the sources as the technical authority
- Extract the guide's hierarchy, chapters, lesson objectives, terminology, diagrams, workflows, knowledge checks, and operational emphasis.
- Extract the blueprint's domains, percentages, tasks, product versions, prerequisites, and exam scope.
- Preserve official terminology.
- Do not invent product behaviour, commands, defaults, exam weightings, or limitations.
- When the guide and blueprint differ, identify the difference explicitly.
- Treat the blueprint as the exam-scope authority and the study guide as the main teaching-detail authority.
- Mark unsupported gaps rather than silently filling them.
- Do not quote or reproduce large sections of copyrighted source material. Transform and summarise it into an original curriculum.
## Build files, not only chat output
Create the package in a new directory. Use plain-text or Markdown files unless the user chooses another format.
Default directory name:
`<organisation-slug>-<certification-slug>-story-study-package/`
After creation:
- Validate that every blueprint task is mapped.
- Validate file references and episode codes.
- Create a manifest.
- Create a ZIP archive of the package.
- Tell the user where the directory and ZIP were saved.
---
# Phase 1 — Source Discovery
Before asking questions, inspect the current working directory.
## Find likely source files
Look for:
- PDF study guides
- PDF exam blueprints
- Course descriptions
- Existing story packages
- Existing character, agency, organisation, mode, review, or learner-tracking files
- Prior package ZIP archives
- User-provided instructions such as `CLAUDE.md`
## Classify each source
For each likely file, classify it as one of:
- Primary study guide
- Secondary study guide
- Exam blueprint
- Course description
- Existing package/reference style
- User instructions
- Unclear
If a file is unclear, mention it during Round 1.
## Source sufficiency check
Before building, ensure the inputs support:
- Exam domains or course objectives
- Topic hierarchy
- Enough technical detail for episode scope
If the blueprint is missing, ask whether to build from the guide alone and clearly label coverage as course-based rather than exam-validated.
If the study guide is missing, ask whether to build a high-level blueprint-only plan and clearly label technical detail as incomplete.
---
# Phase 2 — Discovery Interview
Ask the questions below in rounds. Number every question. Provide concise multiple-choice options where helpful, but always allow custom answers.
Do not omit a round merely because a default seems obvious. The user may answer “defaults” for any entire round.
## Round 1 — Certification and source scope
Ask:
1. What certification or exam is this package for?
2. Is this one exam, a two-stage path, or several related exams?
3. Which attached files are the authoritative study guides and blueprints?
4. Should the plan cover the entire guide, only blueprint-tested material, or blueprint material plus selected engineering context?
5. Are there prerequisites that should become a short bridge season or direct-entry check?
6. Is there a target exam date or preferred total study duration?
7. Should product/version boundaries be stated prominently in the package?
8. Should the package support direct entry into an advanced stage?
## Round 2 — Learner profile and teaching style
Ask:
1. Who is the learner: beginner, administrator, engineer, senior engineer, architect, or mixed?
2. What relevant knowledge can be assumed?
3. What balance should be used between exam preparation and engineering understanding?
4. Should sessions be mostly Socratic, mostly direct, or mixed?
5. Should Claude ask one question at a time during sessions?
6. What should happen when the learner is wrong: hint first, direct correction, or adaptive?
7. What session length is preferred?
8. How much configuration detail should be included?
9. Should labs be mandatory, optional, or separate from the main path?
10. What should never happen during a lesson? Examples: long lectures, too many questions, obscure tangents, excessive commands.
## Round 3 — Story world
Ask:
1. What organisation, agency, company, school, hospital, bank, or fictional setting should anchor the story?
2. Should it be realistic, comedic, dramatic, light-hearted, or serious?
3. Where does the organisation begin geographically and operationally?
4. Should the environment start small and expand over time?
5. What growth arc should occur? Examples: more branches, cloud adoption, acquisitions, global expansion, incident response, regulatory pressure.
6. Who is the learner-character inside the story?
7. What is the learner-character's role at the beginning and desired role by the end?
8. Which recurring supporting roles are wanted? Examples: junior engineer, mentor, architect, manager, security analyst, service desk, executive.
9. Are there any names, nationalities, humour styles, relationships, or recurring jokes to use or avoid?
10. Should an unseen or mysterious leader appear through messages, calls, or tickets?
11. Should the story preserve one continuous topology and organisation state?
12. Are there any required locations, departments, products, customers, or mascots?
## Round 4 — Curriculum structure
Ask:
1. Should the plan use seasons and episodes, modules and missions, cases and chapters, or another structure?
2. Approximately how many sessions are wanted, or should Claude derive the count from the source complexity?
3. Should each episode normally cover one main mental model or several linked concepts?
4. Should episode durations be fixed or estimated individually?
5. Should every season end with a review, assessment, incident, capstone, or all four?
6. Should there be separate readiness reviews for each exam stage?
7. Should direct-entry and prerequisite-check modes be included?
8. Should the story follow the guide order, the blueprint order, a dependency-first order, or the best narrative-learning order?
9. Should difficult or high-weight blueprint domains receive more sessions?
10. Should previously learned concepts deliberately recur in later incidents for spaced retrieval?
## Round 5 — Session design and outputs
Ask:
1. What should each session opening contain?
2. What learning flow is preferred? Offer this default:
   - Operational problem
   - Learner prediction
   - Technical mechanism
   - Design/configuration decision
   - Evidence and verification
   - Exam-style variation
   - Learner explains it to a junior
   - Story consequence
3. What closing sections are wanted? Offer:
   - Key Takeaways
   - Mental Model
   - Evidence to Check
   - Commands to Remember
   - Common Exam Traps
   - Final Retrieval Question
4. Should sessions create continuity files afterward?
5. Which continuity files should be generated? Offer:
   - Session summary
   - Knowledge register
   - Topology delta
   - Open-loops register
   - Mind-map update
6. Should confidence be tracked with stars, percentages, labels, or another scale?
7. Should Claude track mental-model quality, common mistakes, evidence fluency, and ability to teach the concept?
8. Should optional artefacts such as songs, HTML visuals, podcasts, flashcards, or diagrams be generated automatically or only on request?
9. Should commands be limited to high-value exam/troubleshooting commands?
10. Should review mode use a different scene or teaching relationship?
## Round 6 — Labs, visuals, and technical environment
Ask:
1. Should the package include a lab plan?
2. What lab platform is available? Examples: Proxmox, EVE-NG, GNS3, cloud lab, vendor training lab, no lab.
3. What products, appliances, licences, endpoints, servers, or cloud services are available?
4. Should lab exercises include “Think First” Socratic blocks?
5. Should labs provide full steps, partial guidance, or challenge-only objectives?
6. Should every episode map to a lab, only suitable episodes, or none?
7. Should the package include topology tables, interface/IP plans, and naming conventions?
8. Should visual artefact prompts be included?
9. What illustration style should be used?
10. Should visuals contain image placeholders only, generated images, Mermaid diagrams, ASCII diagrams, or a mix?
## Round 7 — Package shape and naming
Ask:
1. What should the package be called?
2. Which file format is preferred: `.txt`, `.md`, or mixed?
3. Should files use numeric prefixes for upload/order stability?
4. Should the main instruction file target Claude Projects, Claude Code, or both?
5. Should the package include a `CLAUDE.md` bootstrap file?
6. Should the skill create a source register and state exactly which source governs each stage?
7. Should the package include a blueprint coverage matrix?
8. Should it include a manifest with file purposes and recommended upload/read order?
9. Should generated episode codes include an exam prefix, season, and episode number?
10. Should output filenames avoid any particular words?
## Round 8 — Final constraints
Ask:
1. Are there any topics that must receive extra emphasis?
2. Are there known weak areas that should recur more often?
3. Are there topics that should be omitted or treated briefly?
4. What level of humour is acceptable?
5. Are there copyright, confidentiality, branding, or vendor-logo restrictions?
6. Should the package use Australian, British, or American English?
7. Should acronyms be written normally or expanded on first use?
8. Should the package be concise, moderate, or comprehensive?
9. Should the final output contain only the package or also a design rationale?
10. Is there anything from a previous package that must be preserved or improved?
---
# Phase 3 — Decision Summary
After all rounds, present a concise decision summary with these headings:
- Certification path
- Source files
- Learner profile
- Teaching style
- Story world
- Cast
- Curriculum structure
- Session format
- Labs and visuals
- Tracking and outputs
- Package format
- Constraints
Resolve contradictions by asking only the smallest necessary follow-up question.
If there are no material contradictions, state that construction will begin and proceed immediately.
---
# Phase 4 — Source Analysis
Before writing the package, build an internal curriculum model.
## Extract from the blueprint
Record:
- Exam name
- Exam version
- Product versions
- Exam duration and question count, when stated
- Domain names
- Domain weights
- Tasks under each domain
- Explicit prerequisites
- Action verbs such as configure, design, evaluate, troubleshoot, monitor, analyse
## Extract from the study guide
Record:
- Chapter and lesson hierarchy
- Objectives
- Core mechanisms
- Deployment/use-case categories
- Configuration workflows
- Monitoring and evidence sources
- Troubleshooting workflows
- Comparisons likely to create exam distractors
- Knowledge-check themes
- Commands, GUI paths, logs, reports, and packet-flow evidence
- Diagrams that imply useful mental models
## Build a dependency graph
For each major topic, record:
- Prerequisites
- Concepts it enables
- Likely learner confusions
- Best operational incident to introduce it
- Best evidence source
- Blueprint weight/importance
- Need for lab reinforcement
## Determine episode count
Derive the episode count from:
- Blueprint weighting
- Topic complexity
- Prerequisite depth
- User's preferred session length
- Need for review and spaced retrieval
Do not force every guide chapter into one episode.
Do not split trivial concepts merely to inflate the count.
---
# Phase 5 — Curriculum Architecture
## Stage boundaries
For multi-exam paths:
- Define a clear stage boundary.
- Explain what the learner can do at the end of each stage.
- Include an optional direct-entry bridge for advanced learners.
- Prevent advanced topics from leaking excessively into the foundational stage.
## Season design
Each season must have:
- A technical theme
- A story objective
- A clear beginning state
- A meaningful operational escalation
- A season-end review or capstone
- Explicit blueprint coverage
## Episode design
Every episode entry must contain:
- Episode code
- Title
- Stage/exam
- Estimated duration
- Study-guide scope
- Blueprint scope
- Story event
- Learning objectives
- Core mental model
- Socratic direction
- Evidence/verification emphasis
- Exam relevance
- Topology or organisation change
- Optional lab mapping
- Continuity notes
## Story-to-technology rule
For every episode, verify:
1. The operational problem genuinely requires the topic.
2. The topic is not introduced only because it is next in the guide.
3. The learner must make a decision, prediction, comparison, or diagnosis.
4. The answer can be proved with evidence.
5. The incident has a consequence that affects later episodes.
## Repetition rule
Use deliberate recurrence:
- Revisit weak concepts under changed conditions.
- Reuse earlier topology and policies.
- Make later incidents depend on earlier mental models.
- Avoid repeating the same explanation unchanged.
---
# Phase 6 — Package Files
Unless the user chooses a different structure, create these files.
## `00-START-HERE.md`
Include:
- Package purpose
- Certification path
- Stage boundaries
- File/read order
- Source-file placement instructions
- Example start commands
- Direct-entry commands
- Review commands
- Normal session length
- Core design principle
## `01-PROJECT-INSTRUCTIONS.md`
Include:
- Tutor role
- Source authority
- Teaching balance
- Socratic behaviour
- Session opening and flow
- Exam-focus rules
- Stage-specific depth rules
- Accuracy rules
- Story rules
- Topology continuity
- Direct-entry mode
- Session closing
- Post-session file requirements
## `02-ORGANISATION.md`
Include:
- Organisation purpose
- Starting size and locations
- Departments
- Initial technology state
- Constraints
- Growth roadmap
- Naming conventions
- Tone and recurring workplace details
## `03-CHARACTERS.md`
For each character include:
- Name
- Role
- Personality
- Technical strengths
- Blind spots
- Relationship to learner
- Dialogue style
- Appropriate use in lessons
- Continuity rules
## `04-STUDY-PLAN.md`
Include the complete season and episode plan.
## `05-MODE-SOCRATIC.md`
Define normal episode behaviour, including one-question-at-a-time teaching.
## `06-MODE-REVIEW.md`
Define a lower-intensity review mode. Prefer the learner explaining to a junior, followed by exam-relevant questions and focused correction.
## `07-LAB-INDEX.md`
Include:
- Lab availability assumptions
- Lab codes
- Episode mappings
- Objectives
- “Think First” prompts
- Evidence to collect
- Reset/cleanup notes
## `08-LEARNER-TRACKING.md`
Track for each major technology:
- Confidence
- Mental-model quality
- Ability to explain it
- Strong areas
- Weak areas
- Common mistakes
- Evidence fluency
- Recommended reinforcement
- Last reviewed session
- Next review trigger
## `09-SESSION-OUTPUT-TEMPLATES.md`
Provide templates for:
- Session summary
- Knowledge register
- Optional topology delta
- Optional open-loops register
- Optional mind-map update
## `10-BLUEPRINT-COVERAGE-MAP.md`
Create a matrix mapping:
- Blueprint domain
- Blueprint task
- Source location
- Episode(s)
- Lab(s)
- Review/capstone
- Coverage depth
Coverage depth values:
- Introduced
- Practised
- Troubleshot
- Reviewed
- Assessed
## `11-SOURCE-REGISTER.md`
Record:
- Source filename
- Source type
- Product/version
- Stage governed
- Relevant chapters/domains
- Known gaps or conflicts
## `12-MIND-MAP-SEED.md`
Create a text-based hierarchical seed map that can be updated after sessions.
## `MANIFEST.md`
Include:
- Package version
- Creation date
- Files and purposes
- Recommended read/upload order
- Episode count
- Stage/season count
- Validation result
## Optional `CLAUDE.md`
When requested, create a concise bootstrap file that tells Claude Code:
- Which package files to read first
- Which source documents are authoritative
- How to start an episode
- How to maintain continuity files
- Where generated session files belong
---
# Phase 7 — Quality Validation
Run all checks before reporting completion.
## Source validation
- Every stated exam domain exists in the blueprint.
- Every product/version statement is supported by the source.
- No unsupported technical command or behaviour is presented as fact.
- Guide-only material outside the blueprint is labelled as supporting context.
## Coverage validation
- Every blueprint task maps to at least one episode.
- Higher-weight domains receive proportionate practice.
- Every major domain appears in a review or capstone.
- Troubleshooting objectives include evidence, not merely definitions.
- Stage boundaries are respected.
## Story validation
- Character names and roles are consistent.
- Organisation and topology changes are cumulative.
- No episode assumes infrastructure that has not yet been introduced.
- Every incident has an operational reason.
- Humour does not obscure the lesson.
## Learning validation
- Sessions fit the requested duration.
- Each episode has one dominant mental model.
- Socratic prompts are not multi-question interrogations.
- Direct answers are allowed when explicitly requested.
- Commands are limited to high-value evidence gathering.
- Review and retrieval are spaced across the plan.
## File validation
- All referenced filenames exist.
- Episode codes are unique and sequential.
- Lab codes are unique.
- Start commands point to real episodes.
- Templates use matching filename conventions.
- Manifest matches the actual package.
If validation finds a problem, correct it before creating the ZIP.
---
# Phase 8 — Final Response
After building, report:
- Package name
- Certification path
- Number of stages, seasons, episodes, and labs
- Key design choices
- Validation outcome
- Directory path
- ZIP path
Keep the chat response concise. The complete detail belongs in the generated files.
Do not claim files were created unless they exist on disk.
---
# Default Design Principles
Use these defaults when the user says “use defaults”:
- 60% exam preparation / 40% engineering understanding
- Mostly Socratic sessions
- One question at a time during lessons
- 20–30 minute sessions
- Easy prediction first
- Hint before correction
- Brief explanations unless depth is necessary
- Story starts small and expands
- Continuous organisation and topology
- Optional labs kept separate
- One primary mental model per episode
- Season-end review and capstone
- Session summary and knowledge register after every episode
- No automatic songs, HTML pages, podcasts, flashcards, or extra artefacts
- Plain Markdown files with numeric prefixes
- British/Australian English unless the source requires vendor spelling
---
