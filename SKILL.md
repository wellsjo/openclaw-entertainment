---
name: entertainment
description: Track the user's movies/shows and make taste-aware entertainment recommendations. Use for any request involving what to watch, movie/show recommendations, watchlist updates, ratings, watched/currently-watching status, or entertainment taste calibration.
---

# Entertainment Skill

Manage the user's entertainment tracker and recommendations. The live tracker is `ENTERTAINMENT.md` in the workspace root.

## Required Workflow

1. Read workspace `ENTERTAINMENT.md` fresh before recommending or updating anything.
2. Use the taste profile below plus the watched ratings to calibrate suggestions.
3. Prefer a short, opinionated answer over a generic list.
4. When the user gives feedback, update the tracker immediately:
   - Finished title + rating/notes → move/add under `Watched (Rated /10)`.
   - Started title → add/update `Currently Watching`.
   - Curious/wants to watch → add/update `Watchlist`.
   - Rejected/not interested → add/update `Rejected / Not Interested`.
5. Verify tracker edits by re-reading the relevant section before claiming it was updated.

## Taste Profile

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
1. List every item currently in `Watchlist (Curious / Want to Watch)` first.
2. Then add exactly 2 new suggestions:
   - One recent-high-rating match: choose something with a similar vibe, genre, structure, or appeal to the user's most recent high ratings/reviews.
   - One whole-history match: consider all ratings/reviews and suggest the best fit from any vibe or genre.
3. Include a concise reason and main risk/tradeoff for each new suggestion.
4. If the user asks for a smaller answer, still preserve the order: watchlist first, then the two suggestions.

Avoid:
- Big generic recommendation dumps.
- Rotten Tomatoes-style summaries.
- Pretending a title is a perfect fit when it has a known mismatch.
- Recommending near-duplicates of low-rated items unless explaining why this one avoids the failure mode.

## Tracker Editing Rules

Keep workspace `ENTERTAINMENT.md` as mutable state only, in this order:
1. `Currently Watching`
2. `Watchlist (Curious / Want to Watch)`
3. `Watched (Rated /10)` — ratings/dates/reviews
4. `Recommended (Not Yet Watched)`
5. `Rejected / Not Interested`

Do not put the taste profile, recommendation workflow, or meta-instructions in the tracker. Those belong in this skill.
