---
name: entertainment
description: Track Wells's movies/shows and make taste-aware entertainment recommendations. Use for any request involving what to watch, movie/show recommendations, watchlist updates, ratings, watched/currently-watching status, or entertainment taste calibration.
---

# Entertainment Skill

Manage Wells's entertainment tracker and recommendations. The live tracker is `/Users/chappy/chappy/ENTERTAINMENT.md`.

## Required Workflow

1. Read `/Users/chappy/chappy/ENTERTAINMENT.md` fresh before recommending or updating anything.
2. Use the taste profile below plus the watched ratings to calibrate suggestions.
3. Prefer a short, opinionated answer over a generic list.
4. When Wells gives feedback, update the tracker immediately:
   - Finished title + rating/notes → move/add under `Watched (Rated /10)`.
   - Started title → add/update `Currently Watching`.
   - Curious/wants to watch → add/update `Watchlist`.
   - Rejected/not interested → add/update `Rejected / Not Interested`.
5. Verify tracker edits by re-reading the relevant section before claiming it was updated.

## Wells's Taste Profile

Strong positive signals:
- Mystery thrillers with engaging plots and real payoff.
- Suspenseful, gritty, short series, especially 1-2 seasons.
- Post-apocalyptic action when it has momentum and world texture.
- Strong acting, writing, casting, atmosphere, and story structure.
- Fun, rewatchable movies; not everything needs to be prestige.
- Horror when it is well-written and not just shock mechanics.
- 70s period pieces / time capsules.

Strong negative signals:
- Artsy symbolism that dodges resolution.
- Style over substance.
- Lazy writing, plot holes, blunt themes, or moralizing instead of story.
- Gratuitous violence without enough substance.
- Forced political or culture-war messaging that feels shoehorned.
- Bleakness alone is not enough; it needs tension, arcs, world-building, or dark humor.

Rating calibration:
- 9-10: elite, memorable, highly aligned; examples include LOTR, The Matrix, Parasite, Gone Girl, Fury Road/Furiosa, Band of Brothers, Chernobyl.
- 8-8.9: strong recommendation tier; gripping, well-made, satisfying enough.
- 7-7.9: good but flawed; acceptable if it matches the mood.
- 6-6.9: watchable but weak writing, pacing, or entertainment value.
- Below 6: avoid similar recommendations unless there is a very specific reason.

## Recommendation Style

Default output:
- Give 1-3 picks, ranked.
- Include the reason each fits Wells specifically.
- Mention the main risk/tradeoff honestly.
- If choosing from his watchlist, say that directly.

Avoid:
- Big generic recommendation dumps.
- Rotten Tomatoes-style summaries.
- Pretending a title is a perfect fit when it has a known mismatch.
- Recommending near-duplicates of low-rated items unless explaining why this one avoids the failure mode.

## Tracker Editing Rules

Keep `/Users/chappy/chappy/ENTERTAINMENT.md` as mutable state only:
- `Currently Watching`
- `Watched (Rated /10)`
- `Watchlist (Curious / Want to Watch)`
- `Recommended (Not Yet Watched)`
- `Rejected / Not Interested`

Do not put the taste profile, recommendation workflow, or meta-instructions in the tracker. Those belong in this skill.
