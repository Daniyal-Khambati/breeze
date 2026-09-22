# Breeze

Log your hikes, lookouts, and trips. Rank them against each other, and see what your friends have been exploring.

Visual style: a retro national-park-poster look crossed with 16-bit game background art — flat, faceted color blocks only (no gradients, no photorealism), a banded sunset sky, layered mountain silhouettes that recede from pale blue-grey to muted blue-purple to a near-black-green treeline, and a rust-orange accent lifted from the recurring hiker sprite's backpack. That hiker — a solid, rounded game-sprite silhouette, not a stick figure — appears throughout the app: a decorative masthead scene above the top bar on every screen, the onboarding hero, and walking further along the trail on the Summit tab as you log real progress toward your region's destinations.

Originally built as a Claude artifact: https://claude.ai/artifact/Lbh6W9M5uuuF6ncuWTCCsZ

## Features

- Log activities (hikes, lookouts, walks, kayaking, camping, biking, swimming, and more) with a title, location, review, and optional photo
- Rank each new activity by swiping (or tapping) through a head-to-head comparison against your existing ones. Each ranked activity shows a 1–5 star rating derived from its position in your list (best = 5 stars, last place = 1 star), recalculated live as your rankings change
- A friend circle: share a short code to add friends, and only see activities from people in your circle
- A featured lists row at the top of the Feed — Top trails, Top swimming spots, Top lookouts, and Top campgrounds for your home region, each opening into a ranked list of places with their locations
- Browse the feed filtered by activity type via a compact dropdown
- Save activities from the feed to a personal bucket list
- **Summit tab**: a gamified, season-themed mountain scene. Set a home region and a figure climbs the mountain as you log and photograph its destinations. A handful of well-known outdoor regions (Finger Lakes NY, Adirondacks, Colorado Front Range, Pacific Northwest) ship with a starter destination list, clearly marked "Suggested" until real logged activity overtakes it; any other region falls back to generic prompts rather than invented place names. A scope toggle broadens the list to everywhere logged, and "Check another region" lets you preview a different region without changing your own.

## Running it

This is a single self-contained `index.html` file. Open it in a browser, or serve it with any static file server:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

Note: the app relies on a `claude.use('db')` / `claude.use('assets')` runtime environment (as provided by Claude artifacts) for shared storage and photo uploads. Outside that environment, it falls back to a message explaining that shared storage isn't available.
