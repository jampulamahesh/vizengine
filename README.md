# VIZENGINE — Engineering Visual Learning Platform

Learn → Visualize → Simulate → Create → Build. A static website (HTML + CSS + JavaScript modules). No build step.

## Run locally
```bash
python3 -m http.server 8080      # then open http://localhost:8080
```
(Opening index.html directly with file:// will not work because browsers block ES modules there.)

## What works today
| Area | Status |
|---|---|
| Home, 17 branches, 37 course cards, search/filter, enrol (local) | Working |
| Visual Learning Lab (engine, gears, neural net, beam, RC) | Working, live computed |
| 3D Lab (Three.js): rotate, explode, section, isolate, labels, measure, assembly steps | Working (needs internet for Three.js CDN + WebGL) |
| 4D Lab: engine cycle, assembly sequence, robot routine, timeline | Working (same CDN note) |
| Simulations (pendulum, projectile, spring, RLC, Otto, Bernoulli, 2-link IK) | Working |
| Project Studio (rule-based scaffold, diagrams, Markdown export) | Working (not AI) |
| Graphic Design Studio (layers, shapes, symbols, PNG/JSON) | Working |
| 3D Printing Lab (STL/OBJ inspect, orientation, time/material estimate) | Working (estimates only) |
| Exam Preparation (step-by-step solver, quiz) | Working |
| VIZ AI chat, AI doubt solver, "Refine with AI" | Needs you to connect an OpenAI-compatible endpoint + key (⚙ Connect AI) |
| Login, Community, cloud save, 3D model storage | NOT included: needs a backend (Supabase/Firebase) |

## Publish on GitHub Pages
1. Create an empty repository on github.com (e.g. `vizengine`).
2. In this folder:
```bash
git init
git add .
git commit -m "VIZENGINE initial version"
git branch -M main
git remote add origin https://github.com/<your-username>/vizengine.git
git push -u origin main
```
3. Repo → Settings → Pages → Source: "Deploy from a branch" → `main` / `/ (root)` → Save.
4. After a minute the site is live at `https://<your-username>.github.io/vizengine/`.

## Security note
An API key typed into the AI settings is stored in the browser (localStorage) and sent from the browser. For a public site, put the key behind your own server/proxy and enter the proxy URL instead.

## Structure
```
index.html  styles.css
js/main.js (router)  util.js  data.js  concepts.js  models.js  viewer.js  stl.js  ai.js
js/pages/  home courses visual lab3d lab4d sims project graphic printing tutor exam dashboard projects community auth
```
