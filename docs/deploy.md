# Deploy (quick)

GitHub Pages (quick):
1. Commit and push these files to the `main` branch.
2. In the repo on GitHub → Settings → Pages → Source: select "main" branch and root folder.
3. After a minute, your site will be at `https://<your-username>.github.io/<repo>`.

Netlify:
1. Create a Netlify account and "New site from Git".
2. Connect GitHub and pick this repo.
3. Set build command: none. Publish directory: `/`.
4. Deploy.

If you want CI or a simple build step (e.g., Sass, bundling), I can add a package.json and simple scripts.
