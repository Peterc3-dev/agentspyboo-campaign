# AgentSpyBoo Campaign

A single-file, self-contained HTML page that presents a personal bug-bounty
learning roadmap as an interactive, gamified checklist.

## What it does

`index.html` renders a dark, terminal/cyberpunk-styled "campaign" UI built with
plain HTML, CSS, and a small amount of vanilla JavaScript. The content is a
five-phase plan (setup -> learn -> first hunt -> practice -> ongoing) for getting
started in web-app bug bounty hunting, framed as quests with rewards.

Interactivity:

- Click a phase header to expand/collapse its quest list.
- Click a quest to toggle it complete; completed quests are dimmed and checked.
- A progress bar and "current phase" indicator update from the number of
  completed quests.

There is no backend, build step, or external code dependency. The only network
request is to Google Fonts for the typefaces.

## Status

Personal/experimental. It is a static info page with a checklist, not a
production tool. Completion state is held in an in-memory object only, so
**progress resets on page reload** (there is no `localStorage` persistence). The
roadmap content is opinionated and hand-written, not generated or validated.

## Run it

Open `index.html` directly in a browser, or serve the folder:

```sh
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Notes / limitations

- Single file (`index.html`); all markup, styles, and script are inline.
- No persistence across reloads (see Status).
- Requires an internet connection only for the Google Fonts stylesheet; the page
  still works offline with fallback fonts.
- The earlier description of this repo as a "Canvas game" was inaccurate — it
  uses no `<canvas>` and is not a game; it is a styled interactive checklist.
