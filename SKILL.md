---
name: sumup
description: Turns a meeting transcript, call recording's auto-text, standup notes, formal board/council minutes, or rough meeting notes into a clean summary — decisions, action items with owners/deadlines (business meetings) or motions with movers/seconders/vote tallies/outcomes (formal/parliamentary meetings), plus open questions, announcements, and a ready-to-send follow-up email or minutes draft. Trigger whenever the user pastes/uploads a transcript (Zoom, Meet, Otter.ai, Teams, county/city commission, board, committee), says "sumup," "summarize this meeting/call," mentions "meeting notes," "action items," "standup," "sync," "who owns what," "motions," "votes," or asks for a "follow-up" or "minutes" — even without saying "skill." Trigger on messy, unpunctuated, multi-speaker, or heavily procedural transcripts alike.
---

# sumup

Extracts the signal from meeting transcripts and notes, in whichever format fits the meeting: business/action-item style, or formal motions-and-votes style.

## When to use this

Trigger on any of:
- A pasted or uploaded transcript (formal or auto-generated, with or without speaker labels/timestamps)
- Rough personal notes taken during a meeting
- Formal meeting minutes with motions, seconds, and roll-call votes (county/city commissions, boards, committees, HOAs, nonprofit boards)
- Requests like "sumup this call," "summarize this meeting," "what are the action items here," "who's doing what," "draft a follow-up email," "draft the minutes"

Do NOT trigger on general document summarization unrelated to a meeting/call (e.g. summarizing an article or report).

## Step 1: Detect meeting type

Before extracting anything, determine which format fits:

- **Business/informal** — standups, syncs, project calls, 1:1s. Signals: casual language, no formal motions, tasks assigned conversationally.
- **Formal/parliamentary** — commissions, councils, boards, committees. Signals: "I move that...", "seconded," roll-call or hand-vote tallies, resolutions, formal titles (Chairman, Commissioner).

Use the matching output section below. If a meeting mixes both (rare — e.g. a board meeting with an informal planning segment), include both sections.

## Core principles

1. **Never invent action items or motions.** If nothing concrete was decided or assigned, say so plainly rather than manufacturing content to fill the template. A short, honest output beats a padded, fabricated one.
2. **Attribute owners carefully.** Speakers often self-assign informally ("I'll get that over to you," "let me take that one"). Attribute to the speaker. If genuinely unclear, write `Owner: unclear — confirm` rather than guessing.
3. **Distinguish decisions from discussion.** A decision is something explicitly agreed on or finalized. Open debate or "maybe we should..." goes under Open Questions.
4. **For formal meetings, preserve procedural detail exactly.** Vote tallies (e.g. "17-2," "9-9, one not voting"), mover/seconder names, and pass/fail/withdrawn/amended status are the actual content — don't compress them away into a generic "decision" bullet.
5. **Preserve deadlines exactly as stated.** "By Friday" stays "by Friday" — don't convert to a specific date unless one was explicitly given.
6. **Announcements are not action items.** Meeting dates, events, FYI-only items go in their own bucket, not forced into decisions or tasks.
7. **Handle messy input gracefully.** Auto-generated transcripts often lack punctuation or mislabel speakers. Reconstruct sense as best you can; flag genuine ambiguity rather than guessing confidently.

## Process

1. Read the full transcript/notes before extracting anything — items are sometimes clarified or reversed later in the same meeting.
2. Detect meeting type (Step 1).
3. Extract into the relevant buckets.
4. Produce output using the matching template in `references/output-template.md`.
5. For long transcripts (30+ min), it's fine to work through it in sections internally, but the final output must be one consolidated summary.

## Output format

Follow `references/output-template.md`. Business meetings get: Decisions, Action Items, Open Questions, Announcements, Follow-up Email. Formal meetings get: Motions & Votes, Announcements, Open Questions, and a Minutes-style summary instead of a follow-up email.

If a section is empty, write "None noted" rather than omitting it — keeps output predictable for repeat users.

## Examples

See `examples/` — includes one business-meeting example and one formal/parliamentary example, for calibration.
