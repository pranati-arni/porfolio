# Pranati Arni — Portfolio

A single-file, interactive portfolio built around a **trajectory rail**: a glowing violet
spine pinned to the left edge that fills as you scroll, with clickable nodes that jump to
each section (About · Projects · Skills · Contact).

Everything lives in **`index.html`** — no build step, no dependencies (fonts load from
Google Fonts CDN).

---

## ✏️ How to edit

### Add a real project
Open `index.html`, scroll to the `projects` array near the bottom (inside `<script>`):

```js
const projects = [
  { title: "My First App", desc: "What it does.", tag: "Web App",
    link: "https://github.com/pranatiarni/my-app", status: "live" },
  ...
];
```

- Copy one `{ ... }` object, fill it in, and end with a comma.
- Set **`status: "live"`** for a real project, or **`"soon"`** for a placeholder card.
- `link` is optional — leave `""` if there's nothing to link yet.

### Fill in your links
In the **Contact** section, the chips marked `is-todo` are placeholders:
- **LinkedIn** — replace `href="#"` with your profile URL.
- **Kaggle / Résumé** — replace the `href`, or delete the chip if you don't want it.

### Change the color
At the very top of the `<style>` block, edit one line:

```css
--accent: #8b5cf6;   /* swap this hex to recolor the whole site */
```

### Other quick edits
- **Tagline** — there's a `TAGLINE SLOT` comment in the hero if you ever want one.
- **Skills** — add `<span class="tag">Tool</span>` chips in the Skills section.
- **Kicker** — the small `Portfolio · Frisco, TX · Est. 2026` line is easy to change or remove.

---

## 🚀 Deploy to Cloudflare Pages

You have two easy options.

### Option A — Direct upload (no Git, fastest)
1. Go to <https://dash.cloudflare.com> → **Workers & Pages** → **Create** → **Pages** → **Upload assets**.
2. Give the project a name (e.g. `pranati-portfolio`).
3. Drag the whole `portfolio` folder (or just `index.html`) into the upload box.
4. Click **Deploy site**.
5. Your site goes live at `https://<project-name>.pages.dev` 🎉

To update later: open the project → **Create new deployment** → upload the new `index.html`.

### Option B — Connect to GitHub (auto-deploys on every push)
1. Push this folder to a GitHub repo.
2. Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
3. Pick the repo. For build settings:
   - **Framework preset:** `None`
   - **Build command:** *(leave empty)*
   - **Build output directory:** `/`
4. **Save and Deploy.** Every `git push` now redeploys automatically.

### After deploying
Update the social-preview URL in `index.html` (near the top):

```html
<meta property="og:url" content="https://your-site.pages.dev" />
```

---

## 📁 Files
| File | Purpose |
|------|---------|
| `index.html` | The entire site — markup, styles, and scripts in one file. |
| `README.md`  | This guide. |
