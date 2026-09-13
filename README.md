# Your personal website (jasmine tea theme)

A plain HTML/CSS site, modeled on the structure of Tommaso Tulkens' page
(About / Research / Teaching), with a "Writing" page skipped as requested.
No build step, no Jekyll, no dependencies — just static files.

## Files

```
index.html          → About / home page
research.html        → Research / projects page
teaching.html        → Teaching page
style.css             → All styling (jasmine tea color palette, fonts, layout)
files/cv-placeholder.txt  → Swap for your real CV (see note inside)
images/               → Put your profile photo here (e.g. images/profile.jpg)
```

Every placeholder is written in plain English inside the HTML (`Your Name`,
`[your institution]`, `you@example.com`, etc.) — just find-and-replace them
with your real details. A few spots also have a small dashed yellow note box
telling you what to do (e.g. in the Research and Teaching sections).

## 1. Fill in your content

Open `index.html`, `research.html`, and `teaching.html` in any text editor
and replace the placeholder text. Key things to update:

- Page `<title>` tags and the `<meta name="description">` in `index.html`
- Your name, title, bio, and interest tags in `index.html`
- The advisor/manager, email, and location fields in the meta panel
- Your photo — add a file to `images/` (e.g. `images/profile.jpg`) and
  replace the dashed placeholder box in `index.html` with:
  `<img src="images/profile.jpg" alt="Portrait of Your Name">`
- Your CV — replace `files/cv-placeholder.txt` with a real PDF and update
  the CV links in all three pages to point to it
- Research and Teaching entries — duplicate or delete the `<li>` blocks in
  `research.html` / `teaching.html` as needed
- If you don't need the Teaching page at all, delete `teaching.html` and
  remove its `<li><a href="teaching.html">Teaching</a></li>` link from the
  nav in the other two files

## 2. Put it on GitHub Pages

1. **Create a repository.** On GitHub, click "New repository." If you want
   the site at `https://<your-username>.github.io/` directly, name the repo
   exactly `<your-username>.github.io`. If you'd rather have it at
   `https://<your-username>.github.io/some-name/`, name it `some-name` —
   this matches how Tommaso's is set up (repo `economics`, served at
   `/economics/`).

2. **Upload the files.** Easiest way if you're not using git from the
   command line:
   - Open your new repo on GitHub → "Add file" → "Upload files"
   - Drag in `index.html`, `research.html`, `teaching.html`, `style.css`,
     the `files/` folder, and the `images/` folder
   - Commit the changes

   Or, with git installed locally:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<repo-name>.git
   git push -u origin main
   ```

3. **Turn on GitHub Pages.**
   - Go to the repo's **Settings** tab → **Pages** (left sidebar)
   - Under "Build and deployment," set **Source** to **Deploy from a
     branch**
   - Set **Branch** to `main` and folder to `/ (root)`, then **Save**

4. **Wait a minute or two**, then GitHub will show you the live URL at the
   top of that same Pages settings screen (it looks like
   `https://<your-username>.github.io/` or
   `https://<your-username>.github.io/<repo-name>/`).

5. **Re-check your links.** Because the site is plain relative links
   (`research.html`, `style.css`, etc.), it will work whether it's served
   from the root of your GitHub Pages domain or from a subfolder like
   `/economics/` — no changes needed either way.

## Notes

- Fonts (Fraunces + Karla) load from Google Fonts via a `<link>` tag in each
  page's `<head>` — no local files needed, but the page will need an
  internet connection to fetch them (they're cached after first load).
- The whole site is three HTML files sharing one stylesheet, so any style
  change you make in `style.css` applies everywhere automatically.
