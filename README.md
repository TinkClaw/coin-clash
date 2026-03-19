# Clash: Meme Coin & Trading Bot Fighting Game

A browser-based fighting game with two modes — meme coins vs trading bots. No dependencies, no build step — just one HTML file and pure Canvas 2D.

**Play now: [tinkclaw.com/clash](https://tinkclaw.com/clash)**

## Game Modes

### Coin Clash — [tinkclaw.com/coinclash](https://tinkclaw.com/coinclash)
Meme coins battle it out. Community-built, open source roster.

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
| TinkClaw | Boss | Beat all 8 to unlock |

### Bot Clash — [tinkclaw.com/botclash](https://tinkclaw.com/botclash)
Trading bots enter the ring. Original characters, zero IP risk.

| Bot | Type | Style |
|-----|------|-------|
| Snipe | Speedster | Precision strikes, fastest execution |
| Gridlock | Tank | Methodical, unbreakable defense |
| Liquidator | Brawler | Heavy hits, melts positions |
| Sandwich | Trickster | Traps opponents, extracts value |
| Arbiter | All-Rounder | Balanced, exploits every gap |
| Flash | Assassin | Massive burst, gone in a flash |
| Whale | Tank | Massive, moves markets |
| DCA | Warrior | Relentless, never stops buying |
| TinkClaw | Boss | Beat all 8 to unlock |

## Features

- 1P vs AI with Easy / Normal / Hard difficulty
- 2P local multiplayer
- Synthesized sound effects (Web Audio API, no files needed)
- Mobile touch controls
- Career stats with localStorage persistence (separate per mode)
- Unlockable boss fighter
- Share results to X
- Combo system, blocking, specials, finishers

## Run Locally

Open `index.html` in a browser. That's it.

URL path determines mode: append `?mode=bot` or `?mode=coin`, or just access `/coinclash` or `/botclash` when deployed.

## Add Your Own Fighter

We welcome community-created fighters! See [CONTRIBUTING.md](CONTRIBUTING.md) for the full guide.

Each fighter needs two things:
1. A **data entry** in the `FIGHTERS` or `BOT_FIGHTERS` array (stats + moves)
2. A **draw function** (Canvas 2D art)

## Tech

- Single HTML file, zero dependencies
- Canvas 2D rendering at 60fps
- Web Audio API synthesized sounds
- No images, no sprites — all characters are drawn with code
- URL-based mode routing (same file serves both modes)

## Disclaimer

Coin Clash is a parody/fan game. Character names reference cryptocurrency communities and are not affiliated with or endorsed by any token project. Bot Clash features original characters.

## License

MIT — see [LICENSE](LICENSE)

---

Built by [TinkClaw](https://github.com/TinkClaw)
