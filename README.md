# Ironline Industrial Parts & Services — website

Static marketing site. No build step: everything Render serves is in `public/`.

```
public/
  index.html    the whole site (HTML + CSS + a little JS)
  favicon.svg
render.yaml     Render Blueprint (static site, publishes ./public)
```

## Preview locally

```
python -m http.server 8000 --directory public
```

Then open http://localhost:8000.

## Deploy on Render

1. Push this folder to a GitHub (or GitLab/Bitbucket) repository.
2. In Render: **New > Blueprint**, pick the repository. Render reads `render.yaml` and creates the static site.
   (Or **New > Static Site**, publish directory `public`, build command blank.)
3. Every push to the main branch redeploys automatically.
4. Custom domain: Render dashboard > the site > **Settings > Custom Domains**.

## Known gap

The contact form only shows a "Request received" message; it does not send the
submission anywhere. Wire it to a form service or a small backend before launch.
