# Pokémon FireRed: Link's Awakening (LinkRed)

**Made by Shawn-Paul**

> What if the hero of Koholint Island got dropped into Kanto, with a sword, and the world remembered what he did?

LinkRed is a big FireRed ROM hack built on the [pokefirered](https://github.com/pret/pokefirered) decompilation. You play **Link**. You can still catch and battle Pokémon, but you also have a sword, hearts, real-time fights and a world that reacts to your kills. Mario creatures are mixed into the game, too.

> ⚠️ **Status: playable work in progress.** Most of it was built without an emulator in the loop, so expect bugs. Please report them (see [Reporting bugs](#reporting-bugs)).

---

## Why LinkRed is different

Most ROM hacks reskin the map, swap the Pokémon or raise the difficulty. LinkRed changes how the game plays and how the world treats you.

| Typical ROM hack | LinkRed |
|---|---|
| Same top-down tile movement | Free 8-direction movement with a sword, spin attack and Pegasus dash |
| Battles happen only in the battle screen | Battles **and** real-time Zelda-style fights on the overworld |
| Losing a wild battle means a whiteout | Losing gives you a **second chance**: finish the Pokémon with your sword |
| Killing is invisible | Kills are counted, and **NPCs, Mom, Oak and the police react** |
| Trainers are only fought by battle | Fight trainers and townspeople by battle **or** by sword |
| New Pokémon are palette swaps | New **Mario Pokémon** with their own evolutions |

---

## Features

### 🗡️ Link's controls

| Input | Action |
|---|---|
| D-pad | Free 8-direction movement |
| **B** | Swing the sword. **Hold** B for a spin attack |
| Hold **A** while walking | Run |
| Run straight for about 40 frames | Pegasus dash (also works with **R**) |
| Hold **A** while standing still | Charge the dash |
| **L** | Help |

Link's sword cuts grass and hits objects, and the dash breaks through things.

### ⚔️ Battle overhaul

- Pokémon, Mario and Zelda mixed together in one battle system, with a reworked menu.
- A **SWORD** command in battle.
- **Mario-style action commands** for Mario moves.
- The Poké Ball throw is kept.
- Every Pokémon has an idle animation, and trainers bob in battle.

### 🍄 Mario creatures

- 12 new Mario species (Pokédex #393–404), each with its own evolution.
- Goomba and Koopa appear on Route 1, shortly after Pallet Town.
- A hand-drawn Mario NPC.
- Custom Mario sound effects.

### ❤️ Real-time field combat (Zelda-style)

- A heart meter on the HUD. You get 3 hearts plus 1 for every 2 badges.
- Knockback, enemy attack wind-ups, bows, and enemy AI such as hopping, walking, floating and swordsmen.
- Hitting an **unbeaten trainer** with the sword starts their battle.
- Hitting an ordinary person makes them **fight back**, some with swords and some with bows.
- Wild Pokémon can be fought with the sword on the field.

### 💀 Second chance

If you **lose a plain wild battle**, you don't white out. The screen closes in, and you're back on the field facing the Pokémon that beat you. **Kill it with your sword** and your lead Pokémon comes back with ¼ HP. If you run to another area, Link collapses and you white out.

### 🩸 Blood and bodies

- Animated blood particles and splats.
- Dead Pokémon tip over, show **X eyes** and lie in a growing pool.
- Mario creatures use their own dead art.
- A spin attack on a person leaves a gory mess.
- Press **A** on a body to dispose of it. Otherwise it's gone the next time you visit the route.

### 🚓 Consequences

Every kill is counted, and the world remembers.

- **Townspeople gossip** about your reputation (they only know once it's bad enough).
- **Mom** and **Professor Oak** turn against you in stages: they notice, then get angry, then kick you out.
- Kill an innocent and the **police** come. Two cops run in, then the chief **interrogates** you. You can confess (fine of ¼ of your money) or deny it (a 50/50 chance of walking free or paying half).

### 🎨 Presentation

- Custom logo "FIRERED: LINK'S AWAKENING".
- "MADE BY SHAWN-PAUL" appears after the logo, on the title screen and in the credits.
- Rival is **Ganon** (default name).
- Link's Awakening sound effects and music, ported to the GBA sound engine.
- Dialogue rewritten for the new world.

---

## Roadmap

- [x] Link movement, sword, spin attack, dash
- [x] Battle overhaul (SWORD command, Mario action commands)
- [x] Mario creatures and their evolutions
- [x] Real-time field combat, hearts, blood and bodies
- [x] Second chance after losing a wild battle
- [x] Kill counters, gossip, Mom/Oak reactions, police and interrogation
- [x] Shawn-Paul branding on the title screen and in the credits
- [ ] Super Mario Bros. 3 style music
- [ ] More Mario creature art and Mario overworld content
- [ ] A girl character (Marin or Zelda)
- [ ] Hearts, enemies and "?" blocks used more widely in the world
- [ ] Balance pass, bug fixes and feedback from players

---

## Playing the game

1. Get an emulator that runs GBA games, such as **mGBA** (free).
2. Open `LinkRed.gba` in the emulator.
3. Start a new game. Link, not a Pokémon trainer, is your character.

> The ROM is built from source. This repository does **not** include any commercial ROM from Nintendo.

### Tips

- Save often. This is a work in progress, and fights can be dangerous.
- Your kills count. Be careful who you swing at.
- After you lose a wild battle, swing your sword at the Pokémon that won.

---

## Building from source

You need a Linux environment (WSL on Windows works) with the ARM toolchain from the [pokefirered install guide](INSTALL.md).

```bash
git clone https://github.com/<your-username>/LinkRed.git
cd LinkRed
make modern -j$(nproc)
```

The ROM is written to `pokefirered_modern.gba`.

### Where the LinkRed code lives

| File | What it does |
|---|---|
| `src/link_player.c` | Link on the field: movement, sword, spin, dash |
| `src/link_battle.c` | Battle overhaul: SWORD command, Mario action commands |
| `src/link_combat.c` | Real-time field fights, bodies, blood, kill counters |
| `src/link_police.c` | Police interrogation scene |
| `data/scripts/link_combat.inc` | Mom, Oak, police and second-chance scripts |
| `tools/link_gfx/` | Python scripts that generate the LinkRed graphics |

---

## Reporting bugs

Open an Issue and include:

- What you were doing and where in the game.
- What you expected, and what happened.
- Whether it happens every time.
- The emulator you used.

---

## Credits

- **Shawn-Paul**: creator, designer, playtester.
- The [pret](https://github.com/pret) team for the pokefirered decompilation this project is built on.
- Game Freak and Nintendo for the original games and characters.

## Legal

LinkRed is an unofficial, non-commercial fan project. It is not affiliated with or endorsed by Nintendo, Game Freak, The Pokémon Company or Creatures Inc. Pokémon, The Legend of Zelda and Mario are trademarks of their respective owners. The source here builds on the pokefirered decompilation, which contains Nintendo's copyrighted game content. Don't distribute built ROMs, and support the official games.
