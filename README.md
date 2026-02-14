# Dragon Repeller — Указания за игра

Кратко описание
- Малка браузър игра: целта е да победиш дракона, който блокира града.

Как да пуснеш играта
- Отвори файла [index.html](build-a-role-playing-game-main-20260213T114226Z-1-001/build-a-role-playing-game-main/index.html#L1) в браузър (двойно клик или Open File в редактор).

Основни елементи на интерфейса
- Три бутона в горната част — техният текст и действие се променят според локацията.
- Полета със статове: `XP` (опит), `Health` (живот), `Gold` (злато).
- По време на битка се показва `Monster Name` и `Monster Health`.

Локации и налични действия
- Town square (градски площад): `Go to store`, `Go to cave`, `Fight dragon`.
- Store (магазин): `Buy 10 health (10 gold)`, `Buy weapon (30 gold)`, `Go to town square`.
- Cave (пещера): `Fight slime`, `Fight fanged beast`, `Go to town square`.
- Fight (битка): `Attack`, `Dodge`, `Run`.

Оръжия и инвентар
- Стартово оръжие: `stick` (power 5). Други: `dagger` (30), `claw hammer` (50), `sword` (100).
- Купуване: оръжие за 30 gold. Когато имаш най-силното оръжие, опцията за втория бутон в магазина се сменя на "Sell weapon for 15 gold".
- Оръжие може да се счупи (≈10% шанс) ако имаш повече от едно — ще загубиш последното добавено оръжие.

Механика на битката
- Когато атакуваш, ти първо поемаш щета от чудовището: зависи от нивото на чудовището и от `xp`.
- Ако твоят удар засече (ок. 80% шанс, или автоматично ако живот < 20), чудовището губи живот, базиран на силата на оръжието и малко случайност, зависеща от `xp`.
- Ако животът ти ≤ 0 — губиш (REPLAY). Ако животът на чудовището ≤ 0 — печелиш (получаваш `gold` и `xp`). Побеждаването на дракона е крайният успех — WIN.

Награди
- При победа над чудовище: `gold += floor(level * 6.7)` и `xp += level`.

Великденско яйце (мини-игра)
- Как да го активираш: след като победиш НЕ-дракон противник (slime или fanged beast), на екрана "The monster screams..." натисни третия бутон (по подразбиране текстът е "Go to town square"), той стартира секретната мини-игра.
- Правила на мини-играта: избираш `2` или `8`. Играта генерира 10 случайни числа (0–10). Ако избраното число присъства сред тях — печелиш 20 gold; иначе губиш 10 health.

Практически съвети
- Побеждавай по-слаби противници първо, за да натрупаш `xp` и `gold`.
- Купувай оръжия и здраве когато имаш достатъчно `gold` (10 за здраве, 30 за оръжие).
- Внимавай за счупване на оръжие — не продавай последното си оръжие.

Рестарт
- Бутонът REPLAY? рестартира стойностите: `xp=0`, `health=100`, `gold=50`, оръжие `stick`.

Файлове
- Основни файлове: [index.html](build-a-role-playing-game-main-20260213T114226Z-1-001/build-a-role-playing-game-main/index.html#L1), [script.js](build-a-role-playing-game-main-20260213T114226Z-1-001/build-a-role-playing-game-main/script.js#L1), [styles.css](build-a-role-playing-game-main-20260213T114226Z-1-001/build-a-role-playing-game-main/styles.css#L1).

Ако искаш, мога да: променя текста на бутона за стартиране на великденската мини-игра (да стане "Secret game"), да добавя подсказка в текста след победа, или да преведа README на английски.
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
