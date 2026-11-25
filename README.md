# Friction

A news-style website that lists the everyday problems people are complaining about, with the evidence behind each one, so you can build the fix.

- **Today's 15**: specific frustrations from recent news, surveys, reviews and forums
- **Personal**: 10 small problems one person runs into that lots of people share
- **My problems**: problems you save or add yourself, with a solution notebook for each
- Each problem has a detail page: what people don't like, the numbers, who it affects, why it happens, what already exists, and idea sparks
- Three scores per problem: **Reach** (how many people), **Growth** (how fast it's getting worse), **Solvable** (how realistic a fix is for a small team)
- Search, filters, sorting, and a light/dark toggle

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole site: layout, styles and code |
| `feed.json` | The day's problems (`topics` = news list, `personal` = personal list) |

## Run it locally

The page loads `feed.json` with `fetch`, so open it through a local server rather than double-clicking the file:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Put it on GitHub Pages

1. Create a repository and add `index.html`, `feed.json` and this README.
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, and save.
4. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

## What works differently outside Claude

The version hosted on Claude has a few features that come from Claude itself. On GitHub:

- **Saved problems, notes and problems you add** are kept in your browser only (localStorage), not synced across devices.
- **The "Solve this with Claude" chat** shows a message saying it isn't available.
- **The daily update** won't reach the GitHub copy. To refresh it, replace `feed.json` with a newer one and commit it.

## Updating the problems

`feed.json` follows a fixed shape. Each problem has an `id`, `title`, `dek`, `category`, `region`, `trend` (`worse`, `steady` or `better`), `scores` (`reach`, `growth`, `solvable` from 1–10), `keyStat`, `whyNow`, `frustration`, `voices`, `stats`, an optional `chart`, `who`, `causes`, `existing`, `sparks` and `sources`. Copy an existing entry as a template.
