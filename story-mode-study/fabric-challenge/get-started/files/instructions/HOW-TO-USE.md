# How to Use This Pack in Claude

## Start the programme

Say:

`Start UFC-01`

Claude should read `CLAUDE-INSTRUCTIONS.md`, the matching session file, and the tracking files.

## Continue

Say:

`Continue UFC-01`

Claude should resume from the current session state rather than restarting.

## Finish a session

After the final challenge question is answered, Claude updates:
- `tracking/KNOWLEDGE-REGISTER.md`
- `tracking/REVIEW-QUEUE.md`
- `tracking/SESSION-LOG.md`

## Start next session

Say:

`Start UFC-02`

## Review

Say:

`Review mode`

Claude should use the review queue and knowledge register, not simply repeat recent session summaries.

## Competition drill

Say:

`UFC challenge mode`

Claude should:
- hide the topic,
- mix domains,
- ask one question at a time,
- reduce hints,
- emphasise recognition, verification and troubleshooting.

## Add official study material later

If official Fortinet study guides, documentation, screenshots, lab notes, or challenge-supporting material are added to the project:

Claude should use those sources to enrich the relevant sessions while keeping the existing session structure.

Exact commands, GUI paths, defaults and verification procedures should be sourced from those materials rather than invented.
