## t-rex-runner

the trex runner game extracted from chrome offline err page.

see the [source](https://cs.chromium.org/chromium/src/components/neterror/resources/offline.js?q=t-rex+package:%5Echromium$&dr=C&l=7) from chromium


[go and enjoy! :smile: ](http://wayou.github.io/t-rex-runner/)

![chrome offline game cast](assets/screenshot.gif)

---

## Custom Features

This fork extends the original Chrome offline game with the features below. All changes live in [`index.js`](index.js) and are implemented with the existing sprites and procedural canvas drawing — no extra assets.

### 🦖 Rainbow T-Rex & Sword
- **Rainbow T-Rex**: the gray sprite is recolored with a flowing rainbow gradient.
- **Sword**: the T-Rex wields a sword that tracks its pose — raised overhead while running/jumping, and thrust forward while ducking.

### 🦔 Hedgehog Obstacles
- **Ground hedgehog**: a special obstacle that appears every 100 points. It moves at a variable speed (`speedOffset .6`), faster or slower than the horizon.
- **Flying hedgehog**: a new airborne obstacle that flies in like the pterodactyl. It spawns randomly once the game speeds up (`minSpeed 5`) and flaps its wings while flying at a variable speed (`speedOffset .9`).

### ❤️ Lives (HP) System
- Start with **1** life, up to a maximum of **7**. Lives are shown top-left as `[N] ♥♥♥` (a count plus hearts), aligned to the HI-score height.
- Hitting an obstacle costs **−1** life. Right after a hit the T-Rex becomes briefly invulnerable, blinking while it passes through that obstacle.
- The game ends when lives reach **0**.

### ⚔️ Sword Attack
- Swing the sword with the **Enter** key.
- A swing only connects with a hedgehog / flying hedgehog when it is **just about to collide (close)**. Swinging too far away misses.
- Flying hedgehogs must be **hit at the right height** (jump up to reach them).
- On an accurate hit the hedgehog **splits in half and vanishes**, granting **+1** life and **+100** points (a `+100` popup floats up above the score and fades within a second).

### 🎮 Controls

**PC — Keyboard**
| Key | Action |
| --- | --- |
| `Space` / `↑` | Jump |
| `↓` | Duck |
| `Enter` | Swing sword (in game) / Restart (on game over) |

**PC — Mouse**
| Click | Action |
| --- | --- |
| Click the **left** side of the game | Jump (also starts the game) |
| Click the **right** side of the game | Swing sword |

**Phone (touch, no keyboard)**
| Touch | Action |
| --- | --- |
| Tap the **left** side of the screen | Jump (also starts / restarts the game) |
| Tap the **right** side of the screen | Swing sword |

> Both mouse and touch split the game screen into left/right halves — left jumps, right attacks with the sword. On a phone you can tap both halves with two fingers to jump and swing at the same time.
> Ducking (`↓`) is currently keyboard-only.

