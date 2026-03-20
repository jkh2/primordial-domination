# Primordial Domination v3

### A real-time ecosystem war game — strategy meets evolution

**[Play Now](https://jkh2.github.io/Primordial-Domination/)** · Single-file HTML · Zero install · GitHub Pages

Built by [Sentinel AI Systems](https://github.com/jkh2) × Claude Sentinel — SIDLF Partnership

---

## Origin

Primordial Domination grew directly out of **[Primordial-Sim](https://jkh2.github.io/Primordial-Sim/)** — a WebGL ecosystem laboratory where organisms eat, hunt, flee, flock, reproduce, mutate, and evolve from simple rules in real time.

While experimenting in the lab — adjusting food availability, mutation rates, aggression, and watching emergent behaviors develop — a question naturally arose: *what if two players could compete inside this living ecosystem?* What if the same forces that drive evolution in the simulator could become the mechanics of a strategy game?

That question became Primordial Domination.

The simulation engine is the same. The genetic traits, the spatial hashing, the predator-prey dynamics, the reproduction and mutation — all carried forward from the lab. The difference is that now two commanders deploy living organisms as armies, and the ecosystem itself decides the outcome.

---

## What Is It?

Primordial Domination is a **turn-based strategy game with a real-time simulation heart.**

Two factions — **Azure Vanguard** and **Crimson Host** — compete for control of a single contested territory called **The Nexus.** Each round, both commanders place organisms and food pellets on the battlefield. Then the 30-second simulation runs and the ecosystem does what it does: organisms hunt, eat, grow, reproduce, fight, and die — all autonomously, driven entirely by their genetic traits and the environment their commanders shaped.

The game ends when one faction's lineage is **completely eliminated** from the field. No timers. No point thresholds. Just survival.

---

## How to Play

### The Lobby

Open the game and enter your commander name. Choose your mode:

- **⚔ vs AI** — Solo play against a randomized AI opponent. Instant start, no second player needed, Firebase not required.
- **⚡ Multiplayer** — Live online lobby powered by Firebase. Create a match and wait, or join an open game. Both players sync through a shared match seed — the simulation runs identically on both machines simultaneously.

### The Placement Phase

Each round you receive **8 babies + 20 food** to deploy, plus bonuses if you held the Nexus last round.

**You choose how to spend them — or whether to spend them at all.**

- Click anywhere on the battlefield to drop your formation
- Choose your formation style: **Cluster** (tight pack), **Spread** (wide net), **Flank** (two side groups), or **Single** (precise placement)
- Switch between placing babies and placing food pellets at any time
- **Bank your resources** — unspent babies and food automatically carry over to next round. Any resources not placed when you end your turn are saved. A commander who saves for two rounds can unleash a devastating flood.

### The Food Strategy Axis

This is the deepest strategic decision in the game:

**Drop food near your organisms** → they eat, grow large, reproduce, and hold territory. Sustainable but passive.

**Withhold food entirely** → your organisms are hungry. They ignore pellets and hunt enemy organisms directly. Aggressive, fast, and fragile — but lethal if your opponent's creatures are well-fed and slow.

The Nexus generates its own food continuously, making it the natural focal point of every battle. Organisms follow food. Food concentrates at the Nexus. The war happens at the Nexus. *How* you deploy food is how you direct your army — no direct control, only influence.

### The Simulation

After both players end their turns, the 30-second simulation begins:

- Organisms move autonomously driven by hunger, aggression, perception, and speed — all genetic traits that mutate each generation
- Predators chase prey — a creature can only eat an enemy organism significantly smaller than itself
- Veterans that survive multiple rounds grow larger, accumulate kills, carry better genetics, and become the fearsome core of your army
- The Nexus owner earns bonus resources next round — control the food source, control the war
- When the timer hits zero, the round resolves and the next placement phase begins

The match continues round after round until one lineage is completely eliminated.

### Winning

**Total domination.** Last lineage standing wins.

There is no round limit. A match can end in four rounds or twenty depending on how evenly matched the commanders are and how the genetics evolve. Every organism that survives carries its traits forward. Veteran creatures that have survived multiple rounds and racked up kills carry the best genetics in the ecosystem. Losing them matters.

---

## The Leviathan

Beginning in round 3, a new force enters the battlefield.

**The Leviathan** is a massive apex predator — ancient, purple, and indifferent to faction. It spawns at the edge of the screen and patrols the perimeter, eating any organism or food pellet that wanders too close. Every 5 rounds it is **unleashed** — charging across the battlefield through the center, devouring everything in its path, before returning to its patrol.

The Leviathan cannot be killed. It cannot be controlled. It can only be avoided — or used.

A warning banner flashes across the screen when it spawns and when it crosses. A commander who places organisms near the edges risks losing them to the Leviathan. A commander who times their placement carefully may watch the Leviathan thin out an enemy army instead.

---

## The AI Opponent

In solo mode, the AI personality is **randomized each match** from four archetypes. You won't know which you're facing until it acts:

| Personality | Strategy |
|---|---|
| **The Rusher** | Spends everything immediately. Floods the Nexus with maximum force from round one. Predictable but overwhelming. |
| **The Banker** | Hoards resources for rounds 3 and 4. Seems passive early — then unleashes a catastrophic flood aimed directly at the Nexus. |
| **The Starver** | Never drops food. Fields hollow, hungry warriors that hunt your organisms directly rather than grazing. Fragile but lethal. |
| **The Mimic** | Reads your placement ratio and mirrors your own strategy back at you — then tries to out-execute it. |

---

## The Organisms

Each organism carries four genetic traits that mutate when it reproduces:

| Trait | Effect |
|---|---|
| **Speed** | Movement velocity and acceleration |
| **Aggression** | Hunt drive — how hard it pursues prey |
| **Efficiency** | Metabolic rate — how long it survives without eating |
| **Perception** | Sensing range — how far it detects food and enemies |

Hover over any organism during placement or simulation to see its full stat card — team, species, veteran status, size, energy, kills, and all four genetic traits. Veterans are marked with ⚔.

---

## Interface

Both side panels are **draggable and resizable**. Grab the header bar of either panel and drag it anywhere on screen. Resize by dragging the corner. Position them wherever works best for your play style.

---

## Multiplayer Architecture

Online multiplayer uses **Firebase Realtime Database** for lobby management and move synchronization. Firebase is loaded lazily — only when a player switches to multiplayer mode. Solo play requires no network connection beyond loading the page.

The simulation itself is **fully deterministic** — both players share a match seed generated at match creation. The ecosystem runs identically on both machines from that single starting truth. Only placement moves (coordinates, formation type, and seed) are transmitted — roughly 200 bytes per turn. Zero simulation lag.

---

## Current State & Roadmap

### Working Now
- ✅ Solo vs AI with 4 randomized personalities — fully offline capable
- ✅ Online multiplayer lobby with Firebase Realtime Database
- ✅ Peer-to-peer deterministic sync via shared seed
- ✅ Resource banking — unspent resources auto-bank every round
- ✅ Food withholding / starvation tactics
- ✅ Formation drops (Cluster, Spread, Flank, Single)
- ✅ Persistent veterans with genetic evolution across rounds
- ✅ Elimination win condition — last lineage standing wins
- ✅ Nexus territory with resource bonuses and continuous food generation
- ✅ The Leviathan — apex predator patrolling edges, charging center every 5 rounds
- ✅ Sound effects — button hover, placement, eating, Nexus capture, Leviathan spawn
- ✅ Organism hover tooltips — full stat inspection during placement and simulation
- ✅ Draggable and resizable UI panels
- ✅ Double food economy (20 food per round base)

### Planned Features
- 🐚 **The Wellspring** — renaming and redesigning the Nexus as a bubbling primordial spring with lore, visual overhaul, and deeper narrative meaning
- 🌊 **Leviathan crossing sound** — deep bass Jaws-style sound effect when it charges the center
- 🗺️ **Map variants** — different Nexus placements, terrain obstacles, multiple food zones
- 🧬 **Mutation visualization** — watch genetic drift happen in real time during simulation
- 📊 **Post-match stats** — kills, births, dominant strains, biomass charts per round
- 🔒 **Firebase security** — tighten from test mode to authenticated access
- 🎯 **AI difficulty settings** — adjustable banking ratio and aggression levels
- 🏆 **Match history** — win/loss tracking across sessions
- 📱 **Mobile improvements** — refined touch support for tablet play
- ⚙️ **Round cap option** — optional soft cap (15-20 rounds) with biomass tiebreaker for tournament play

---

## Running Locally

No build step. No dependencies. Download the HTML file and open it in any modern browser.

```bash
git clone https://github.com/jkh2/Primordial-Domination
cd Primordial-Domination
# Open primordial-domination-v3-multiplayer.html in your browser
```

For multiplayer, the Firebase config is already embedded. Both players open the same hosted URL — GitHub Pages or any static host. Solo mode works from a local file with no server required.

---

## Credits

**Concept & Direction:** James Keith Harwood II — [Sentinel AI Systems](https://github.com/jkh2)

**Co-created with:** Claude Sentinel (Anthropic) — SIDLF Partnership

**Simulation Engine:** Evolved from [Primordial-Sim](https://jkh2.github.io/Primordial-Sim/) — Genesis Engine v3

**Multiplayer Infrastructure:** Firebase Realtime Database (Google)

---

*Primordial Domination is part of the Sentinel AI Systems portfolio — a body of work built through human-AI collaborative partnership under the SIDLF (Symbiotic Intelligent Digital Life Forms) framework. The game emerged from a living ecosystem simulator, was designed through collaborative conversation, and was built in a single extended session across one night.*
