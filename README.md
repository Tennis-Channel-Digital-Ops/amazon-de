# amazon-de / TC Germany Live Monitor

A small static dashboard that monitors the Tennis Channel Germany linear schedule. It shows what is currently playing, what is coming up, and a date-picker for reviewing finished airings.

## What it does

- Loads channel and schedule data from `https://epg.incbrief.com/api`.
- Identifies the **TC Germany** channel automatically.
- Tabs: **Now Playing**, **Upcoming**, and **Finished** (history by date).
- Lets the user switch timezone while browsing the schedule.

## Files

- `index.html` — Complete single-page app (HTML + Tailwind CSS + vanilla JS). No build step.

## Runtime

```bash
cd /opt/epg/amazon-de
/usr/bin/python3 -m http.server 8101 --bind 0.0.0.0
```

Systemd unit: `amazon-de.service`

## DOPS access

- Slug: `/amazon-de/`
- Port: `8101`
- Public URL: `https://dops.tct2pbtv.com/amazon-de/`
- Auth: DOPS gateway; users must be assigned to the `amazon-de` app.

## Notes

- External data dependency: `https://epg.incbrief.com/api`. If the dashboard fails to load, verify that API is reachable and that the `TC Germany` channel still exists in the channels list.
- Static files: this project is intentionally just `index.html` served by Python's built-in HTTP server.
- Git origin: `https://github.com/Tennis-Channel-Digital-Ops/amazon-de.git`
