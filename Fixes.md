ALL OF US ARE DEAD — GAMEPLAY REFERENCE

Ranimated Roblox Experience | Standalone Recreation

1. GAME IDENTITY

- Original reference: All of Us Are Dead by Ranimated.
- Current experience ID: "9759729519".
- Older V1 experience ID: "8694898220".
- Target recreation engine: Godot 4.
- Objective: Create an original standalone survival game inspired by the observed gameplay, using independently developed code, models, animations, UI and environments.

2. CONFIRMED GAMEPLAY FEATURES

- The core gameplay revolves around surviving successive days against zombies.
- The environment includes a school building, corridors, classrooms and outdoor grounds.
- The game supports multiplayer.
- The current experience catalogue lists a maximum server capacity of eight players.
- The visible HUD includes player health, a kill counter, a survival-day indicator, a countdown and a currency display.
- The recorded gameplay shows health displayed as "100/100".
- The game includes a shop or upgrade interface and a progression economy.
- Zombies are the principal enemies.

3. HISTORICAL V1 INFORMATION

The older V1 experience description provides additional historical details. These must not automatically be assumed to apply to the current version.

- Death in V1 is described as causing accumulated progress to be lost.
- V1 describes progression through successive survival days.
- V1 mentions Blue Fire as a currency/reward system.
- Historical reward descriptions include rewards for killing groups of enemies and contributing to boss defeats.
- V1 references a Blood Moon event and a special infected enemy.
- Historical descriptions indicate that enemy difficulty and available progression develop as survival advances.

4. MOVEMENT SYSTEM — DETAILS TO VERIFY

The available recording does not establish every movement state. The recreation should use a configurable movement system until further gameplay evidence is collected.

Potential states to investigate:

- Idle.
- Walking.
- Running or sprinting.
- Jumping.
- Falling.
- Attacking.
- Taking damage.
- Death.

Still unknown:

- Exact movement speeds.
- Whether sprinting consumes stamina.
- Whether jumping is enabled.
- Whether movement is camera-relative.
- Whether movement speed changes during combat.

5. ZOMBIE SYSTEM — DETAILS TO VERIFY

Confirmed: Zombies are the primary enemies.

Unverified:

- Exact enemy health and damage values.
- Enemy movement speeds.
- Detection and pursuit distances.
- Attack frequency.
- Enemy variations and special abilities.
- Whether enemy difficulty scales with each survival day.
- Exact boss mechanics.

For development, implement configurable enemy attributes and independent AI states rather than hardcoding unverified values.

6. HEALTH AND DEATH — DETAILS TO VERIFY

Confirmed from footage:

- The player HUD displays health as 100/100.

Historical V1 information:

- Death is described as resetting accumulated progress.

Current-version details still requiring confirmation:

- Whether death resets the day counter.
- Whether currency is retained.
- Whether players can revive teammates.
- Whether players can rejoin an ongoing session.
- Whether an individual death ends only that player's run or affects the entire team.

7. SHOP AND ECONOMY

Confirmed:

- A shop or upgrade interface is visible.
- The game has a currency display.
- Progression and upgrades are part of the gameplay loop.

Historical V1 information:

- Blue Fire is mentioned as a reward currency.
- Historical descriptions mention kill-related and boss-related rewards.

Unverified:

- Current currency name and exact reward values.
- Shop categories and item availability.
- Exact prices.
- Whether upgrades are temporary or permanent.
- Whether currency is shared between players.
- Whether progression persists between sessions.

8. MULTIPLAYER SYSTEM

Confirmed:

- The current experience catalogue lists up to eight players per server.
- The footage shows multiple player characters.

Unverified:

- Whether kills and rewards are individually or collectively credited.
- Whether currency is shared.
- Whether players can revive one another.
- Whether players collide.
- Whether the survival-day countdown is server-wide.
- Whether players can join after a run has started.

9. SURVIVAL AND DAY PROGRESSION

The visible HUD establishes a survival-day counter and a countdown.

The recreation should support:

- A day progression system.
- A countdown between survival phases.
- Increasing survival difficulty as a configurable design feature.
- A shared multiplayer survival session.

Exact day durations, enemy spawn quantities, difficulty curves and rewards remain unverified.

10. IMPLEMENTATION REQUIREMENTS

Build the standalone recreation with modular, configurable systems:

1. Player controller and animation state machine.
2. Third-person camera.
3. Zombie AI and navigation.
4. Health and damage management.
5. Survival-day manager.
6. Enemy spawning and difficulty configuration.
7. Currency and progression manager.
8. Shop and upgrade interface.
9. Multiplayer session management.
10. HUD and countdown interface.
11. Death and respawn management.
12. Event system for special survival phases.

Use configuration files or exported Godot variables for unknown statistics and economy values. Avoid presenting invented values as verified original-game data.

11. EVIDENCE AND DEVELOPMENT RULES

Use the following labels throughout development:

- CONFIRMED: Directly visible in the supplied gameplay footage or supported by the relevant current-version reference.
- HISTORICAL: Documented for the older V1 experience but not confirmed for the current version.
- INFERRED: A reasonable interpretation of observed gameplay.
- UNVERIFIED: Requires additional gameplay footage or direct testing.

IMPORTANT: The current Ranimated experience is the primary reference. Historical V1 information is supplementary and must be clearly distinguished. The recreation must use original code and independently created assets rather than copying proprietary game files.
