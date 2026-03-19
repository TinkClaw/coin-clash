# Coin Clash: Mortal Meme Combat

A browser-based fighting game where meme coins battle it out. No dependencies, no build step — just one HTML file and pure Canvas 2D.

**Play now: [tinkclaw.com/coinclash](https://tinkclaw.com/coinclash)**

## Fighters

| Fighter | Type | Style |
|---------|------|-------|
| Doge | All-Rounder | Much balance, very fight |
| Pepe | Trickster | Rare and unpredictable |
| Shib | Speedster | Lightning fast striker |
| Bonk | Brawler | Heavy hits, big damage |
| Wif | Tank | Dog with a hat, hard to kill |
| Floki | Warrior | Viking fury, axe combos |
| Trump | Showman | Big moves, huge finisher |
| Samo | Assassin | Silent and deadly |
| TinkClaw | Boss | Beat all 8 fighters to unlock |

## Features

- 1P vs AI with Easy / Normal / Hard difficulty
- 2P local multiplayer
- Synthesized sound effects (Web Audio API, no files needed)
- Mobile touch controls
- Career stats with localStorage persistence
- Unlockable boss fighter
- Share results to X
- Combo system, blocking, specials, finishers

## Run Locally

Open `index.html` in a browser. That's it.

## Add Your Own Fighter

We welcome community-created fighters! See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide.

The short version: each fighter needs two things:
1. A **data entry** in the `FIGHTERS` array (stats + moves)
2. A **draw function** (Canvas 2D art)

## Tech

- Single HTML file, zero dependencies
- Canvas 2D rendering at 60fps
- Web Audio API synthesized sounds
- No images, no sprites — all characters are drawn with code
- ~2000 lines of vanilla JS

## License

MIT — see [LICENSE](LICENSE)

---

Built by [TinkClaw](https://tinkclaw.com) | Powered by $TKCL
