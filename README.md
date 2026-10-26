# First-half scoring model (web app)

A static, single-file app. It runs entirely in the browser, so no server or build step is needed.

## Host it on GitHub Pages

1. Create a new GitHub repository (public, or private if your plan supports Pages on private repos).
2. Upload `index.html` and `README.md` to the repository root.
3. Go to **Settings → Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose `main` and `/ (root)`, then save.
4. After a minute, the site is live at `https://<your-username>.github.io/<repo-name>/`.

## Use it

- **Try sample data** runs a demo on synthetic games.
- Or upload a history CSV with these columns: `date, league, home_team, away_team, home_h1_points, away_h1_points`, plus `home_h1_` and `away_h1_` versions of `fgm, fga, 3pm, fta, oreb, dreb, tov`. Optional: `half_minutes`.
- Optionally upload an upcoming-games CSV with `date, league, home_team, away_team` to get predictions.

## Notes

- Features use only games played before each game's date, and validation uses a chronological holdout.
- The model is a ridge regression ported from the Python version. Results can differ slightly because of numeric details.
- Team names must be spelled consistently within a league.
