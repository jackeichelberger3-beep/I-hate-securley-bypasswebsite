# Game Hub (static) — quick instructions

What this is
- A small static site that lists games as separate HTML files inside `games/`.
- The hub loads each game inside an iframe modal (no external URLs displayed).

How to add a new game (step-by-step)
1. Copy `games/game-template.html` → `games/my-new-game.html`.
2. Edit the copied file (it is a standalone HTML page that can include CSS and JS).
3. Open `script.js`. Add an entry to the `games` array:
   {
     id: "mygame1",
     title: "My Game",
     desc: "Short description.",
     file: "games/my-new-game.html"
   }
4. Save and open `index.html` via a static server (see below).

Notes
- Keep games inside the `games/` folder so paths are predictable.
- The hub intentionally does not display URLs—only game titles/descriptions.
- Each game file is standalone and permanent in the code. Copy templates to make more.

Serving locally
- From the project folder run:
  - Python 3: `python -m http.server 8000`
  - Then open `http://localhost:8000/index.html` in your browser.
- Or use VS Code Live Server, or host on any static hosting (GitHub Pages, Netlify).

Security & sandboxing
- The iframe uses `sandbox="allow-scripts allow-same-origin"` for simple games.
- If your game needs other features (e.g., popups), adjust sandbox attributes responsibly.

That's it — copy the template to make as many game pages as you want and register them in script.js.
