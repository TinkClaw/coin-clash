# Contributing a Fighter to Coin Clash

Want to add your favorite meme coin to the roster? Here's how.

## What You Need

Every fighter has two parts:

1. **Fighter data** — stats, moves, and metadata (added to the `FIGHTERS` array)
2. **Draw function** — Canvas 2D code that renders your character

## Step 1: Fighter Data

Add an entry to the `FIGHTERS` array in `index.html`. Here's the template:

```js
{
  id: 'mytoken',           // lowercase, unique identifier
  name: 'MyToken',         // display name
  type: 'Brawler',         // archetype (for display)
  style: 'Short tagline',  // shown on character select
  color: '#ff6600',        // primary color (hex)
  outline: '#cc4400',      // darker outline color
  boss: false,             // true = unlockable boss
  w: 52,                   // hitbox width (44-58)
  h: 80,                   // hitbox height (74-86)
  hp: 110,                 // health points (85-140)
  spd: 4,                  // movement speed (3-7)
  def: 5,                  // defense rating (2-9)
  moves: {
    punch:    { name: 'Jab',      dmg: 8,  startup: 4,  active: 6,  recovery: 8,  range: 55, color: '#ffcc00' },
    kick:     { name: 'Kick',     dmg: 11, startup: 6,  active: 5,  recovery: 10, range: 60, color: '#ffaa00' },
    special:  { name: 'Special',  dmg: 18, startup: 10, active: 8,  recovery: 14, range: 70, color: '#ff8800' },
    finisher: { name: 'FINISHER', dmg: 45, startup: 8,  active: 10, recovery: 16, range: 65, color: '#ff4400',
                launch: true, shakeScreen: true, unblockable: true }
  }
}
```

### Stat Guidelines

Keep stats balanced. Use existing fighters as reference:

| Archetype | HP | SPD | DEF | Notes |
|-----------|-----|-----|-----|-------|
| Speedster | 85 | 7 | 2 | Glass cannon, fast startup frames |
| Tank | 140 | 3 | 9 | Slow but hard to kill |
| All-Rounder | 110 | 4 | 5 | Balanced across the board |
| Brawler | 130 | 3 | 7 | High damage, slow recovery |
| Assassin | 90 | 6 | 3 | High burst, low sustain |

### Move Properties

Every move has these required fields:

| Field | Description |
|-------|-------------|
| `name` | Display name for the move |
| `dmg` | Damage dealt |
| `startup` | Frames before the hit connects |
| `active` | Frames the hitbox is active |
| `recovery` | Frames of cooldown after |
| `range` | How far the attack reaches (pixels) |
| `color` | Color of the hit effect |

Optional move modifiers:

| Modifier | Description |
|----------|-------------|
| `projectile: true` | Fires a projectile. Add `projSpd` and `projColor` |
| `teleport: true` | Teleports behind opponent |
| `dash: 150` | Rushes forward N pixels during the move |
| `multihit: 4` | Hits multiple times |
| `shield: true` | Blocks incoming damage |
| `launch: true` | Pops the opponent into the air |
| `shakeScreen: true` | Screen shake on hit |
| `unblockable: true` | Cannot be blocked (finishers only) |
| `leaps: true` | Small hop during the attack |

## Step 2: Draw Function

Create a function named `drawYourFighter` that renders your character using Canvas 2D:

```js
function drawMyToken(ctx, x, y, w, h, data, f, breathe, walk, armExt, legExt, frame) {
  // ctx     - Canvas 2D context
  // x, y    - character position (feet center)
  // w, h    - hitbox dimensions
  // data    - fighter data object
  // f       - facing direction: 1 = right, -1 = left
  // breathe - idle bob animation (small float, ~0 to 3)
  // walk    - walk cycle offset (oscillates when moving)
  // armExt  - 0 to 1, punch/special extension
  // legExt  - 0 to 1, kick extension
  // frame   - global frame counter

  // Use the helper functions:
  // drawRoundBody(ctx, x, y, rx, ry, fill, stroke) - oval body
  // drawLimb(ctx, x1, y1, x2, y2, width, color)    - arm/leg
  // drawFist(ctx, x, y, r, color)                   - hand/foot
  // drawEyes(ctx, x, y, facing, r, pupilR, gap)     - pair of eyes
}
```

Then register it in the `DRAW_FNS` object:

```js
const DRAW_FNS = {
  // ... existing fighters ...
  mytoken: drawMyToken,
};
```

### Art Guidelines

- Use only Canvas 2D primitives (arcs, ellipses, rects, paths) — no images or sprites
- Use `f` (facing) to flip the character horizontally: multiply x-offsets by `f`
- Animate `armExt` for punches (fist extends forward) and `legExt` for kicks
- Use `breathe` for idle animation (subtle body bob)
- Use `walk` for leg movement when moving
- Keep the character within the `w x h` hitbox
- Use colors that match your `color` and `outline` from the fighter data
- Look at `drawDoge` or `drawPepe` in the source as examples

## Step 3: Submit

1. Fork this repo
2. Add your fighter data + draw function to `index.html`
3. Test locally — make sure the character select screen renders your fighter and combat works
4. Open a PR with:
   - Fighter name and concept
   - Screenshot of your fighter on the select screen
   - Brief description of their playstyle

## Rules

- Keep it fun — meme coins, internet culture, crypto mascots
- No NSFW content
- No hateful or discriminatory content
- Stats must be balanced (we'll review during PR)
- Draw functions must use Canvas 2D only (no external assets)

## Questions?

Open an issue or find us at [tinkclaw.com](https://tinkclaw.com).
