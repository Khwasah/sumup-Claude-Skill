# sumup-Claude-Skill
Turn any meeting — informal team sync or formal parliamentary/board meeting — into a clean, structured summary. No manual digging through transcripts.
Why

Every team has this problem: the meeting ends, the transcript is a wall of text, and someone has to manually work out who owes what, what got decided, and what's still open. sumup does that extraction automatically — and it's one of the few tools that also correctly handles formal meetings with motions, seconds, and roll-call votes (county commissions, boards, HOAs, nonprofit boards), not just casual standups.

Before → After
Business meeting — see examples/sample-input-1.txt → examples/sample-output-1.md (decisions, action items with owners/deadlines, follow-up email draft)
Formal/parliamentary meeting — see examples/sample-input-2.txt → examples/sample-output-2.md (motions, movers/seconders, vote tallies, outcomes, minutes-style summary)
Install
Download SKILL.md and the references/ folder from this repo.
Add it to your Claude Skills per Anthropic's skill instructions.
Paste any transcript, or say "sumup this," and it triggers automatically.
What it handles
Formal transcripts (Zoom, Teams, Meet) and messy auto-generated ones
Multi-speaker crosstalk and unlabeled speakers
Implicit ownership ("I'll take that one" → attributed correctly)
Formal motions, seconds, amendments, and vote tallies
Long transcripts (30+ min)
Meetings with zero action items or motions (won't fabricate content to fill the template)

License
MIT
