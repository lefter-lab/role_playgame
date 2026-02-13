# Build a Role Playing Game

This repository contains a small browser-based role-playing game (HTML, CSS, JavaScript).

## Live Demo

- Deployed on Netlify: https://build-arpg-20260213-114226.netlify.app

## How to run locally

1. Install Node.js (optional for a simple local server).
2. In the project folder (`build-a-role-playing-game-main`) you can run a simple static server:

```powershell
npx http-server -p 8080
# or
# python -m http.server 8080
```

Open http://localhost:8080 in your browser.

## How to deploy

- Drag & drop the `build-a-role-playing-game-main` folder at https://app.netlify.com/drop
- Or use Netlify CLI: `npx netlify deploy --prod --dir="build-a-role-playing-game-main"`

## How to play (English)

- Goal: Defeat the dragon.
- You start in the Town Square. The UI shows your XP, Health and Gold at the top.
- Buttons:
  - The three main buttons change depending on location (town, store, cave, fight).
  - In the Town Square you can go to the Store, go to the Cave, or Fight the Dragon.
- Store:
  - `Buy 10 health (10 gold)` — spend gold to restore health.
  - `Buy weapon (30 gold)` — buy a stronger weapon to increase attack power.
  - `Go to town square` — return.
- Cave:
  - Choose a monster to fight: Slime, Fanged Beast or return to town.
- Fight:
  - `Attack` — hit the monster. You will also take damage based on the monster's level.
  - `Dodge` — try to avoid an attack.
  - `Run` — return to the town square.
- Defeating monsters gives XP and gold. Defeating the dragon wins the game. If your health reaches 0 you lose and can restart.

## Notes

- The web version is static and runs in a browser. The Electron executable in the project was created to run the same site as a standalone Windows app.
- If you want me to enable automatic Netlify deploy from this GitHub repo, I can add a `netlify.toml` and connect the site.

## Credits

- Based on a beginner JavaScript tutorial and examples.
