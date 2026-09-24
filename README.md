# tebo.games

Gear notes and theorycrafting tools for **tebo.games**.

- **Brand Hub:** [https://tebo.games/](https://tebo.games/)
- **Once Human:** [https://tebo.games/once-human/](https://tebo.games/once-human/)
- **Build Creator & Damage Calc:** [https://tebo.games/once-human/creator.html](https://tebo.games/once-human/creator.html)
- **Gear Catalog:** [https://tebo.games/once-human/catalog.html](https://tebo.games/once-human/catalog.html)
- **In-Browser Admin CMS:** [https://tebo.games/once-human/admin/](https://tebo.games/once-human/admin/)

---

## How It Works

1. **No Backend Required:** The whole site is pure static HTML/CSS/JS deployed automatically via **Cloudflare Pages**.
2. **Database:** All items, weapons, armor, mods, and builds live as clean JSON records in `/once-human/data/`.
3. **No Per-Build Formatting:** Builds are rendered dynamically from structured data into Once Human-themed HUD cards and breakdown pages.
4. **Damage Estimator:** The Creator allows selecting weapon + calibration + mods with live burst and sustained DPS calculations.

---

## Editing Content in the Browser (No Git Needed!)

When you want to add or update gear from your notes:

1. Open `https://tebo.games/once-human/admin/` in your browser.
2. Click **Sign in with Token**.
3. Create a GitHub Personal Access Token (classic with `repo` permission, or fine-grained with Contents read/write on this repo).
4. Sveltia CMS gives you friendly forms for **Builds**, **Weapons**, **Mods**, and **Deviations**.
5. Click **Save** / **Publish** — it commits the new JSON records to GitHub automatically, and Cloudflare Pages redeploys the site in seconds!

---

## Cloudflare Pages Setup (One-Time)

1. Log in to [Cloudflare Dashboard](https://dash.cloudflare.com/).
2. Navigate to **Compute (Workers) > Workers & Pages** > **Create application** > **Pages** > **Connect to Git**.
3. Select this repository: `haitebodesu/tebo.games`.
4. Build Configuration:
   - **Framework preset:** `None`
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/` (or leave empty)
5. Click **Save and Deploy**.
6. Under your Pages project settings, go to **Custom domains** and add `tebo.games`.

---

## Local Preview

You can preview the site locally using any simple web server:

```powershell
# Using Python
python -m http.server 8080

# Or npx serve
npx serve .
```

Then visit `http://localhost:8080/` or `http://localhost:8080/once-human/`.
