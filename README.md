# ⚓ CHOKEPOINT

A browser-based tower defense game set in the world's most contested maritime straits. Build coastal defenses on land, hold the line as hostile ship waves push through the channel.

## Play

**[▶ Play Now](https://naklitechie.github.io/chokepoint/)** — Runs directly in your browser.

⭐ **Like it?** Give this repo a star!

---

## Run Locally

Just open `index.html` in any modern browser. No server needed.

```bash
# Option 1: Double-click the file
open index.html

# Option 2: Local server
python3 -m http.server 3000
# Then open http://localhost:3000
```

No build step, no npm, no config — single HTML file.

---

## Gameplay

- **Select a tower** from the build bar, then **click any land cell** (brown terrain) to place it
- **Right-click** a placed tower to sell it for 50% of its cost
- Click **▶ SEND WAVE** to release the first wave of enemy ships
- After each wave clears, the next wave auto-launches after a 15-second build window
- Lose a **life** for every ship that reaches the exit — you start with 20
- Earn **gold** for each kill; spend it on more towers

---

## Towers

| Tower | Cost | Range | Damage | Fire Rate |
|-------|------|-------|--------|-----------|
| 🛡️ Watch Post | $50 | 3 | 8 | Fast |
| ⚓ Naval Gun | $150 | 5 | 25 | Medium |
| 🚀 Missile Battery | $300 | 7 | 80 | Slow |

Sell any tower for 50% of its build cost by right-clicking it.

---

## Enemy Ships

| Ship | HP | Speed | Reward | Appears |
|------|----|-------|--------|---------|
| 🚤 Patrol Boat | 50 | Fast | $10 | Wave 1+ |
| 🚢 Cargo Ship | 150 | Medium | $18 | Wave 3+ |
| 🛢️ Tanker | 400 | Slow | $30 | Wave 5+ |
| ⚔️ Destroyer | 250 | Fast | $25 | Wave 7+ |

Wave composition scales with wave number — early waves are patrol-heavy, later waves mix in tankers and destroyers.

---

## Maps

| Map | Location | Threat |
|-----|----------|--------|
| 🗺️ Strait of Hormuz | Persian Gulf | IRGCN hostile fleet |
| 🗺️ Bab el-Mandeb | Red Sea / Yemen | Houthi missile boats |
| 🗺️ Malacca Strait | Singapore / Malaysia | Pirate armada |
| 🗺️ Taiwan Strait | Taiwan / China | PLA naval convoy |

Each map uses a real-world satellite basemap (Leaflet + CartoDB Voyager tiles) with an accurate land/water mask. Enemy ships follow a hardcoded BFS path through the navigable water channel.

---

## Features

- 🗺️ Real-world chokepoint maps — same geography as [Strait Command](https://github.com/NakliTechie/strait-command)
- 🚢 4 enemy types with distinct HP, speed, and reward profiles
- 🏗️ 3 tower types with range preview on placement
- 💰 Gold economy — earn from kills, spend on towers, sell for half
- ⏱️ 15-second build window between waves; click to send early
- 📡 Map-specific geopolitical news ticker
- 🌊 Wave difficulty scales automatically — no wave cap

---

## See Also

**[Strait Command](https://github.com/NakliTechie/strait-command)** — same maps, different genre. A naval strategy game set in the same chokepoints.

---

## Planned

- **Adaptive enemy paths** — between waves, enemy ships reroute around heavily defended corridors, probing for gaps in your coverage. Towers become high-cost zones in the pathfinder; open water stays cheap. Players watch the path indicator shift and pre-empt it.
- Additional maps (Suez Canal, Bosphorus, Panama Canal)
- Tower upgrade tiers
- Special abilities (airstrike, naval bombardment)

---

## Tech Stack

- Single HTML file (~800 lines)
- [Leaflet.js 1.9.4](https://leafletjs.com/) — map rendering
- CartoDB Voyager tiles — light theme satellite basemap
- Vanilla JavaScript — no frameworks, no build step
- Canvas 2D — game rendering overlay

---

## License

Public domain / MIT — use it however you want.

---

*"Hold the strait. Do not let them through."*
