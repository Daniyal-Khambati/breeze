# Breeze

Log your hikes, lookouts, and trips. Rank them against each other, and see what your friends have been exploring.

Visual style: ported from a design mockup (`design/breeze-mock.html`) into the app itself. A hand-authored `<canvas>` scene — a dithered sunset sky, a glowing sun, volumetric cumulus clouds, distant birds, tiered pines, bushes, riverside rocks, and a river receding to the horizon, all shaded with a flat-tone-bands-plus-fine-grain-dithering technique rather than smooth gradients — is pinned behind the app (`#heroFixed`) while the screen's content scrolls in a separate sheet on top of it (`.content-sheet`), so the art is progressively covered as you scroll rather than scrolling away with it. The palette (warm paper, a rust accent, lake/moss/near-mtn tag colors), the Bevan/DM Sans font pairing, and pixel-grid icons are pulled into the shared design tokens and reused across the featured-category row, activity-card type tags, and bottom nav. Every ranked activity's card also carries a trail-progress bar with a tiny hiker sprite riding it, next to its "#N of M" badge — the same wayfinding motif as the Summit tab's own mountain widget, which still runs on its earlier flat-SVG renderer.

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
