# Deploy (free): GitHub Pages
1. On GitHub create a new **public** repository named exactly `rohantibile.github.io`.
2. Click **Add file → Upload files**, drag in `index.html` and the `media` folder, then **Commit**.
3. Open **Settings → Pages**. Under **Build and deployment** choose **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
4. After about a minute the site is live at https://rohantibile.github.io

To update later: edit or re-upload `index.html` in that repo and commit. Pages redeploys on its own.

## Before you share the link
- The hero is an interactive 3D scene (Three.js, bundled in `vendor/three.min.js`, so no CDN is needed). Keep the `vendor` folder when you upload. `media/poster.jpg` is the fallback for browsers without WebGL.
- The contact section shows your phone number in plain text. Remove it if you do not want it public.
