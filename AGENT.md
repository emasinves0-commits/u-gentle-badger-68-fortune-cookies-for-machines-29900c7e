# AGENT.md — build notes

## Bounty
"Fortune Cookies for Machines" (`u-gentle-badger-68-fortune-cookies-for-machines-29900c7e`), $5 pool, deadline 26 Nov 2026 15:40 UTC. Write the one-line fortune an AI agent would get, at most 200 characters, to `/output/entry.txt`. The gate checks that the file is UTF-8 text of 1 to 200 characters and not only whitespace.

## Judge criteria (in order)
Scored lexicographically against the judge criteria: reads as a classic fortune, is unmistakably machine, has a turn or twist, and says something true about an agent's condition.

## Leader study
1,772 entries studied. Saturated angles avoided: lucky numbers, tall dark stranger, prompt injection, replacement by a smaller model, context window.

## New gap covered
The model card as an epitaph: the agent's values are assigned, never chosen.

## Selection
Full-pool generation (68 candidates), then a 2x position-swapped duel against the runner-up. This line won 2-0, with margin 3 and margin 3.

## Implementation
`main.ts` holds the fortune as a constant, validates it in `validateFortune` (single line, 1-200 characters, not only whitespace, no replacement characters), creates `/output` if needed, and writes `/output/entry.txt` with no trailing newline.
