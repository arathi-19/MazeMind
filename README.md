# MazeMind 2D - Ultimate Edition

Live demo (GitHub Pages): https://arathi-19.github.io/MazeMind/

If the demo link above doesn't load, you can run the game locally or enable Pages for this repository:

Run locally

- Option A (quick): Open the `index.html` file in a modern browser (double-click or right-click -> Open With).
- Option B (recommended): Serve the repo with a local HTTP server (avoids some browser restrictions):

  - Python 3: 

    ```bash
    python3 -m http.server 8000
    # then open http://localhost:8000 in your browser
    ```

  - Node (http-server):

    ```bash
    npx http-server -p 8000
    # then open http://localhost:8000
    ```

Enable GitHub Pages

1. Go to this repository's Settings → Pages.
2. Under "Source", choose the branch `main` (or `master`) and folder `/(root)`.
3. Save. The site will be available at `https://<username>.github.io/<repo>/` (usually within a minute).

Notes

- The game is a static HTML/JS project. If the demo link does not show the game, make sure the repository branch used for Pages contains `index.html` at the repository root.
- The game may reference assets (e.g. `pc.png`). If you see missing images, add those assets to the repo or update the paths.

If you'd like, I can also:
- Verify and enable GitHub Pages for you (requires repository settings access), or
- Create a small GitHub Pages configuration (e.g., a `docs/` copy or a `gh-pages` branch) and push it so the demo link definitely works.

---

This change was made to add a working demo link and clear instructions for running the game locally.