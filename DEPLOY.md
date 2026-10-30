# Publish the dashboard on GitHub Pages

`index.html` is the whole site (one file, works without a server). It holds result numbers and the strongest cue words per language, no article text and no raw data. The live demo box is switched off in this copy.

## Steps (Command Prompt)

1. On github.com create a new **public** repository, for example `fake-news-audit-dashboard`, empty (no README, no licence).
2. In Command Prompt:

```
cd /d C:\Users\Vinay\projects\mlfn\site
git init -b main
git add index.html .nojekyll DEPLOY.md
git commit -m "Fake-news accuracy audit dashboard"
git remote add origin https://github.com/YOUR_USERNAME/fake-news-audit-dashboard.git
git push -u origin main
```

   If git asks who you are: `git config --global user.name "Your Name"` and `git config --global user.email "you@example.com"`, then run the commit again.
3. In the repository: Settings > Pages > Build and deployment > Source: "Deploy from a branch" > Branch: `main`, folder `/ (root)` > Save.
4. After about a minute the site is at `https://YOUR_USERNAME.github.io/fake-news-audit-dashboard/`.

## Rebuild after new results

```
python -X utf8 -W ignore scripts\build_dashboard.py
```

This rewrites `site\index.html`; commit and push it again.

## Check before making it public

* The page is a project-review result, not a finished paper: the fake-class reading comes from word lists and has not been checked by humans, and the Tamil corpus has no licence. Say so if you share the link.
* It names the public datasets and papers it uses; it contains no team names or student IDs.
* Everything on the page can be copied by anyone with the link.
