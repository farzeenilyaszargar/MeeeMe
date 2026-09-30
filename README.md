# MeeeMe

A small personal time dashboard. Plain HTML, CSS, and JavaScript — no dependencies, accounts, API, or database.

- Create tasks for today with a custom description and time goal.
- Organize tasks into custom groups and activity tags (Athletics → Running, Swimming, Gym).
- Open a task to start, pause, or resume its stopwatch. Only one timer runs at a time.
- Timers continue across refreshes and closed tabs until paused. Time crossing midnight is attributed to each day.
- See weekly hours by day, group, and activity. Browse earlier weeks.
- Edit tasks and groups. Removing a task preserves recorded time.
- Export and import JSON backups from the groups menu.

Everything is stored in `localStorage` in the current browser and origin. Nothing is sent to a server. Clearing browser data removes your history; export a backup to keep a copy. A different browser, device, or website origin has its own separate data.

## Run locally

From this directory:

```sh
python3 -m http.server 5173 --directory dist --bind 127.0.0.1
```

Open http://127.0.0.1:5173. No build step is required. Host the `dist` directory on any static web host. The `.openai/hosting.json` manifest configures private Sites hosting; no runtime services are used.

Dates use your device's timezone. Weekly summaries run Monday through Sunday. Custom activity tags aggregate time across tasks; untagged tasks aggregate by task name within their group.

## Vercel

Import this GitHub repository with the repository root as the Root Directory. The included `vercel.json` selects the Other framework preset, skips build and dependency installation, and serves the existing `dist` directory. Pushes to `main` redeploy the site automatically when the Vercel Git integration is connected.
