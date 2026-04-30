---
name: entertainment
description: Track the user's movies/shows and make taste-aware entertainment recommendations. Use for any request involving what to watch, movie/show recommendations, watchlist updates, ratings, watched/currently-watching status, rejected/not-interested titles, or entertainment taste calibration.
---

# Entertainment Skill

Manage the user's entertainment tracker and recommendations. The live tracker is `ENTERTAINMENT.md` in the workspace root.

## Required Workflow

1. Read workspace `ENTERTAINMENT.md` fresh before recommending or updating anything.
2. Use the tracker's `Taste Profile` section plus watched ratings/reviews to calibrate suggestions.
3. Prefer a short, opinionated answer over a generic list.
4. When the user gives feedback, update the tracker immediately:
   - Finished title + rating/notes → move/add under `Watched (Rated /10)`.
   - Started title → add/update `Currently Watching`.
   - Curious/wants to watch → add/update `Watchlist`.
   - Rejected/not interested → add/update `Rejected / Not Interested`. If the user says they do not want to watch something, dislikes the premise, or wants it removed from consideration, put it there with the reason.
   - Taste preference/rating calibration feedback → update `Taste Profile` in `ENTERTAINMENT.md`.
5. Verify tracker edits by re-reading the relevant section before claiming it was updated.

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

Keep workspace `ENTERTAINMENT.md` as mutable state in this order:
1. `Taste Profile` — user-specific likes/dislikes/rating calibration.
2. `Currently Watching`.
3. `Watchlist (Curious / Want to Watch)`.
4. `Watched (Rated /10)` — ratings/dates/reviews.
5. `Recommended (Not Yet Watched)`.
6. `Rejected / Not Interested`.

Do not put personal taste data directly in this skill. The skill should define the workflow; `ENTERTAINMENT.md` owns the user's taste profile and watch state.
