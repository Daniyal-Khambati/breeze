# Breeze

Log your hikes, lookouts, and trips. Rank them against each other, and see what your friends have been exploring.

Originally built as a Claude artifact: https://claude.ai/artifact/Lbh6W9M5uuuF6ncuWTCCsZ

## Features

- Log activities (hikes, lookouts, walks, kayaking, camping, biking, swimming, and more) with a title, location, review, and optional photo
- Rank each new activity by swiping (or tapping) through a head-to-head comparison against your existing ones
- A friend circle: share a short code to add friends, and only see activities from people in your circle
- A stories row at the top of the Feed — tap a friend's avatar for a full-screen, auto-advancing recap of their recent activities
- Browse the feed filtered by activity type via a compact dropdown
- Save activities from the feed to a personal bucket list

## Running it

This is a single self-contained `index.html` file. Open it in a browser, or serve it with any static file server:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

Note: the app relies on a `claude.use('db')` / `claude.use('assets')` runtime environment (as provided by Claude artifacts) for shared storage and photo uploads. Outside that environment, it falls back to a message explaining that shared storage isn't available.
