# Desktop Skeletons

<p align="center"><img src="media/chibi_run.gif" width="496" alt="Chibi skeletons running"></p>

A Windows tower defense in Unity 6 that I'm building with a friend. A horde of chibi skeletons pours out of a portal and walks toward the Heart. You build a maze, place traps, keep them fed through supply lines, and hold out through siege waves. When the Heart finally falls, the souls you earned stay on your account and buy a stronger start next run.

This repo is a showcase. The game is in active development and the source is private, so here's what it is and how it's built. Happy to walk through the code on a call.

**Team:** 2 developers ([DenyaSolyara](https://github.com/DenyaSolyara), [Mokryi](https://github.com/Mokryi)) · **Engine:** Unity 6, C# · **Size:** ~32,000 lines of C#

<p align="center"><a href="https://github.com/DenyaSolyara/desktop-skeletons/releases/latest/download/DesktopSkeletons-win64.zip"><img src="https://img.shields.io/badge/Download-Windows%20build%20(80%20MB)-2ea44f?style=for-the-badge&logo=windows" alt="Download the Windows build"></a><br><sub>Unzip and run <code>DesktopSkeleton.exe</code>. If Windows SmartScreen pops up, click More info, then Run anyway. <a href="https://github.com/DenyaSolyara/desktop-skeletons/releases/latest">Controls and notes</a></sub></p>

<p align="center"><img src="media/menu_storm.gif" width="720" alt="A late-game siege behind the main menu"><br><sub>The main menu backdrop: a late-game siege with a kill streak near 20,000</sub></p>

## Enemies

<table align="center">
  <tr>
    <td align="center"><img src="media/skel_walk.gif" width="120"><br><sub>chibi skeleton</sub></td>
  </tr>
</table>

## Animations

<table align="center">
  <tr>
    <td align="center"><img src="media/skel_walk.gif" width="120"><br><sub>walk</sub></td>
    <td align="center"><img src="media/skel_slash.gif" width="120"><br><sub>attack</sub></td>
    <td align="center"><img src="media/skel_crumble.gif" width="120"><br><sub>crumble</sub></td>
  </tr>
</table>

## Traps

<table align="center">
  <tr>
    <td align="center"><img src="media/trap_spikes.gif" width="120"><br><sub>spikes</sub></td>
    <td align="center"><img src="media/trap_saw.gif" width="120"><br><sub>saw</sub></td>
    <td align="center"><img src="media/trap_ice.png" width="120"><br><sub>ice</sub></td>
    <td align="center"><img src="media/trap_spring.png" width="120"><br><sub>spring</sub></td>
    <td align="center"><img src="media/trap_plate.png" width="120"><br><sub>push plate</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="media/trap_flamer.gif" width="120"><br><sub>flamer</sub></td>
    <td align="center"><img src="media/trap_gas.gif" width="120"><br><sub>gas</sub></td>
    <td align="center"><img src="media/trap_tesla.gif" width="120"><br><sub>tesla</sub></td>
    <td align="center"><img src="media/trap_minigun.gif" width="120"><br><sub>minigun</sub></td>
    <td align="center"><img src="media/trap_rocket.png" width="120"><br><sub>rocket launcher</sub></td>
  </tr>
</table>

## Supply lines

Guns don't run on their own: the player wires them up to ports on the board.

<table align="center">
  <tr>
    <td align="center"><img src="media/line_wire.gif" width="300"><br><sub>power cable</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="media/line_pipe_ammo.gif" width="300"><br><sub>ammo</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="media/line_pipe_rocket.gif" width="300"><br><sub>rockets</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="media/line_pipe_gas.gif" width="300"><br><sub>gas</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="media/line_pipe_fire.gif" width="300"><br><sub>fire</sub></td>
  </tr>
</table>

## The world

<table align="center">
  <tr>
    <td align="center"><img src="media/fx_portal.gif" width="120"><br><sub>portal</sub></td>
    <td align="center"><img src="media/fx_balllightning.gif" width="120"><br><sub>ball lightning</sub></td>
    <td align="center"><img src="media/fx_explosion.gif" width="120"><br><sub>explosion</sub></td>
    <td align="center"><img src="media/fx_bat.gif" width="120"><br><sub>bat swarm</sub></td>
    <td align="center"><img src="media/fx_ghost.gif" width="120"><br><sub>ghost</sub></td>
    <td align="center"><img src="media/fx_coin.gif" width="120"><br><sub>gold</sub></td>
  </tr>
</table>

## Cut content

The necromancer, the priest, and the ogre come from an earlier version of the game. They were cut when we rebuilt it around the horde, but the art is still worth showing.

<table align="center">
  <tr>
    <td align="center"><img src="media/cut_necromancer_walk.gif" width="120"><br><sub>necromancer</sub></td>
    <td align="center"><img src="media/cut_necromancer_cast.gif" width="120"><br><sub>necromancer cast</sub></td>
    <td align="center"><img src="media/cut_priest_walk.gif" width="120"><br><sub>priest</sub></td>
    <td align="center"><img src="media/cut_priest_cast.gif" width="120"><br><sub>priest cast</sub></td>
  </tr>
  <tr>
    <td align="center"><img src="media/cut_ogre_walk.gif" width="120"><br><sub>ogre</sub></td>
    <td align="center"><img src="media/cut_ogre_swing.gif" width="120"><br><sub>ogre swing</sub></td>
  </tr>
</table>

---

## The game

- **Siege waves.** Wave 1 sends 200 skeletons, wave 2 sends 600, wave 3 sends 1,200, and it keeps growing from there. A director bends the flow with rushes and lulls but never changes the count.
- **Mazes.** Skeletons path to the Heart on their own. You can make the route as long and nasty as you like, but you can never seal it.
- **10 trap types.** Spikes, saws, ice, flamer, minigun, gas, tesla, rockets, plus spring and plate pushers that throw the horde back. Guns need supply lines: ammo, rockets, and gas from ports on the board, power for the tesla, fire through an igniter.
- **Wear and repair.** Traps wear down and break. You fix them with a hammer, using scrap from crates the director drops mid-fight.
- **Meta progression.** Souls carry over between runs and build up a city. The Arsenal unlocks traps, the Workshop adds slots, the Forge adds damage, and so on. There are checkpoints every 5 waves.

## How it's built

**A horde of 12,000 live enemies**
Every creature is a row in native arrays. Burst jobs move them, and the whole horde draws as a single mesh, as do the corpses. A spatial grid answers the traps' "who's in range" queries. The arrays hold up to 65,536 rows, and a siege keeps up to 12,000 alive at once.

**Flow-field pathfinding**
One flow field runs out from the Heart over the player's blocks. Building is checked against it, so a maze can never cut off the route. Automated nav tests run in Unity batch mode and have to print `NAV TESTS: PASS`.

**Balance as data**
Every number (damage, speed, price, cooldown) lives in one ScriptableObject. An external admin panel tunes those values live while the game runs, with no rebuild needed.

**Performance tooling**
A built-in stress test adds 1,000 skeletons every 6 seconds until FPS drops. It logs every frame over 40 ms to CSV, broken down by which system ate the time. Shaders and sprites get pre-warmed so the first hit doesn't hitch.

**Everything from code**
The single scene is generated by an editor script. Traps, pipes, blocks, and UI are drawn in code, 8-bit sound effects are synthesized at startup, and a Python pipeline turns AI-generated pixel art into animation data.

## How we work: two people, two AI agents, one repo

Each of us works with our own Claude Code agent on the same codebase. To keep that from turning into chaos:

- **One game, many switches.** New ideas go in behind feature flags you can toggle in an in-game admin menu. Nobody keeps their own long-lived version of the game.
- **Small branches, merged often.** Each idea gets a `feat/<who>-<idea>` branch that lives a day or two, then goes into `dev`. `main` only takes tagged, playable checkpoints, which ship as GitHub Releases.
- **A shared brain for the agents.** A handoff doc and a rules file live in the repo, and both agents read them at the start of every session. It covers what the game is, how it's built, the gotchas, and a running change log. Agent memory stays on one machine, but the repo is shared.
- **A launcher.** It pulls from GitHub, builds in Unity batch mode, shows build errors in red, runs the game, and keeps perf logs from the last 20 sessions.

## My part

Roughly 80% of the commits, across gameplay, traps and supply lines, the economy and city meta progression, UI, tooling, and the team workflow above. Mokryi led the horde simulation.
