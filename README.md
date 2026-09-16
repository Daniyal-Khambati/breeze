# Wanderlist

Rank your hikes, lookouts, kayak trips and more against each other, and see what your friends have been up to.

Originally built as a Claude artifact: https://claude.ai/artifact/Lbh6W9M5uuuF6ncuWTCCsZ

## Features

- Log activities (hikes, lookouts, walks, kayaking, camping, biking, swimming, and more) with a title, location, review, and optional photo
- Rank each new activity against your existing ones with a quick head-to-head comparison flow
- Browse a feed of activities logged by friends, filterable by type
- Save activities from the feed to a personal bucket list

## Running it

This is a single self-contained `index.html` file. Open it in a browser, or serve it with any static file server:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

Note: the app relies on a `claude.use('db')` / `claude.use('assets')` runtime environment (as provided by Claude artifacts) for shared storage and photo uploads. Outside that environment, it falls back to a message explaining that shared storage isn't available.
