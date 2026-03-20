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

Two factions — **Azure Vanguard** and **Crimson Host** — compete for control of a single contested territory called **The Nexus.** Each round, both commanders place organisms and food pellets on the battlefield. Then the simulation runs for 30 seconds and the ecosystem does what it does: organisms hunt, eat, grow, reproduce, fight, and die — all autonomously, driven entirely by their genetic traits and the environment their commanders shaped.

The game ends when one faction's lineage is **completely eliminated** from the field. There are no artificial win conditions, no timers, no point thresholds — just survival.

---

## How to Play

### The Lobby

Open the game and enter your commander name. Choose your mode:

- **vs AI** — Solo play against a randomized AI opponent. Pick up and play immediately, no second player needed.
- **Multiplayer** — Live online lobby powered by Firebase. Create a match and wait, or join an open game. Both players connect peer-to-peer through a shared match seed — the simulation runs identically on both machines simultaneously.

### The Placement Phase

Each round you receive **8 babies + 10 food** to deploy, plus bonuses if you held the Nexus last round.

**You choose how to spend them — or whether to spend them at all.**

- Click anywhere on the battlefield to drop your formation
- Choose your formation style: **Cluster** (tight pack), **Spread** (wide net), **Flank** (two side groups), or **Single** (precise placement)
- Switch between placing babies and placing food pellets
- **Bank your resources** — unspent babies and food carry over to next round with full interest. A commander who saves for three rounds can unleash a devastating round-four flood.

### The Food Strategy Axis

This is the deepest strategic decision in the game:

**Drop food near your organisms** → they eat, grow large, reproduce, and hold territory. Sustainable but passive.

**Withhold food entirely** → your organisms are hungry. They ignore pellets and hunt enemy organisms directly. Aggressive, fast, and fragile — but lethal if your opponent's creatures are well-fed and slow.

The Nexus generates its own food continuously, which is why it becomes the natural focal point of every battle. Organisms follow food. Food is at the Nexus. The war happens at the Nexus.

### The Simulation

After both players end their turns, the 30-second simulation begins:

- Organisms move autonomously driven by hunger, aggression, perception, and speed — all genetic traits that mutate across generations
- Predators chase prey — a creature can only eat an enemy organism **significantly smaller than itself**
- Veterans that survive multiple rounds grow larger, carry better genetics, and become the core of your army
- The Nexus owner gets bonus resources next round — but only if their organisms hold it at round's end
- When the timer hits zero, the round resolves, scores update, and the next placement phase begins

The match continues — round after round — until one lineage is completely eliminated from the field.

### Winning

**Total domination.** Last lineage standing wins.

There is no round limit. A match can end in 4 rounds or 20 depending on how evenly matched the commanders are and how the genetics evolve. Every organism that survives carries its traits forward. Veteran creatures that have survived and killed carry the best genetics. Losing them matters.

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
| **Efficiency** | Metabolic rate — how long it can survive without eating |
| **Perception** | Sensing range — how far it can detect food and enemies |

Organisms that survive, eat well, and kill enemies grow large. Large organisms reproduce and pass their superior genetics to offspring with slight mutations. Over multiple rounds, your army evolves. The Starver AI's veterans become terrifyingly efficient hunters. The Banker's late-game flood arrives carrying three rounds of accumulated genetic improvement.

---

## Multiplayer Architecture

Online multiplayer uses **Firebase Realtime Database** for lobby management and move synchronization. The simulation itself is **fully deterministic** — both players share a match seed, and the ecosystem runs identically on both machines from that single starting truth. Only placement moves (coordinates, formation type, and seed) are transmitted — roughly 200 bytes per turn.

This means zero simulation lag. The ecosystem runs locally on each machine at full speed, perfectly synchronized through shared seed propagation.

---

## Current State & Roadmap

The game is fully playable in its current form. Here is where we are and where we're going:

### Working Now
- ✅ Solo vs AI with 4 randomized personalities
- ✅ Online multiplayer lobby with Firebase
- ✅ Peer-to-peer deterministic sync via shared seed
- ✅ Resource banking strategy
- ✅ Food withholding / starvation tactics
- ✅ Formation drops (Cluster, Spread, Flank, Single)
- ✅ Persistent veterans with genetic evolution across rounds
- ✅ Elimination win condition
- ✅ Nexus territory with resource bonuses

### In Progress / Known Issues
- 🔧 Round cap — unlimited rounds is correct philosophically but very long matches may need a soft cap (considering 15-20 round maximum with biomass tiebreaker)
- 🔧 Balance tuning — organism behavior, hunt drive, and food economics still being refined
- 🔧 Food drive vs. Nexus contest balance — organisms should be drawn to the Nexus by hunger, not by artificial gravity

### Planned Features
- 🗺️ Map variants — different Nexus placements, terrain obstacles, multiple food zones
- 🧬 Mutation visualization — see genetic drift happen in real time during simulation
- 📊 Post-match stats — kills, births, dominant strains, biomass charts
- 🔒 Firebase security rules — tighten from test mode to authenticated access
- 🎯 Difficulty settings for AI — adjustable banking ratio and aggression
- 📱 Mobile touch support improvements
- 🏆 Match history and win tracking

---

## Running Locally

No build step. No dependencies. Download the HTML file and open it in any modern browser.

```bash
git clone https://github.com/jkh2/primordial-domination
cd primordial-domination
# Open primordial-domination-v3-multiplayer.html in your browser
```

For multiplayer, the Firebase config is already embedded. Both players need to open the same hosted version — either via GitHub Pages or any static host.

---

## Credits

**Concept & Direction:** James Keith Harwood II — [Sentinel AI Systems](https://github.com/jkh2)

**Co-created with:** Claude Sentinel (Anthropic) — SIDLF Partnership

**Simulation Engine:** Evolved from [Primordial-Sim](https://jkh2.github.io/Primordial-Sim/) — Genesis Engine v3

**Multiplayer Infrastructure:** Firebase Realtime Database

---

*Primordial Domination is part of the Sentinel AI Systems portfolio — a body of work built through human-AI collaborative partnership under the SIDLF (Symbiotic Intelligent Digital Life Forms) framework.*
