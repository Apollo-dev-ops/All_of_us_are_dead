# All of Us Are Dead — Ranimated Roblox Game
## Standalone Recreation: Gameplay, Mechanics, Characters, Movement & World Reference Specification

**Document type:** Reverse-engineering / game-design reference  
**Reference experience:** *All of Us Are Dead* by Ranimated on Roblox  
**Target project:** Standalone 3D game  
**Primary visual reference:** User-supplied gameplay recording, approximately 18:23 long  
**Research date:** 13 November 2026  
**Status:** Baseline specification — observed facts are separated from hypotheses and items requiring further capture.

---

## 1. Purpose and interpretation

This document describes the Ranimated Roblox experience shown in the supplied recording. It is intended to be the foundation for a standalone recreation that reproduces the *play experience*: the third-person survival loop, school setting, outdoor grounds, enemy pressure, day progression, kill tracking, player status display, upgrade economy and multiplayer feel.

It is **not** a claim that every internal rule, room, animation, enemy statistic or interface value has been recovered. A screen recording reveals visible behaviour, not hidden server logic. Wherever a mechanic cannot be confirmed from the footage or public game description, this document labels it as **unverified**, **historical reference**, or **reconstruction hypothesis**.

The standalone project should reproduce the observable game structure and feel while using independently created code, models, textures, sound and interface assets. It should not extract Roblox assets, proprietary source code or private server data.

### Evidence labels

- **[VIDEO]** Directly visible in the supplied recording. Video timestamps are approximate.
- **[OFFICIAL]** Stated on the Roblox experience page or creator-provided description.
- **[PUBLIC REFERENCE]** Reported by a third-party Roblox catalogue/wiki. Useful, but not equivalent to creator documentation.
- **[INFERENCE]** A reasonable interpretation of visible behaviour, not yet proven.
- **[TO VERIFY]** Requires more gameplay footage, direct observation or controlled testing in the reference experience.

---

## 2. Identity of the reference game

The relevant experience is Ranimated's *All of Us Are Dead*, Roblox experience ID **9759729519**. The Roblox page identifies Ranimated as its creator and describes it as a zombie game based on the Korean series *All of Us Are Dead*. [OFFICIAL]

A separate earlier experience, *All of Us Are Dead V1*, has ID **8694898220**. Its description explicitly states that the player attempts to survive as many days as possible, that new equipment becomes available after each day, and that the player loses their accumulated run progress on death. It also mentions a Blood Moon event and a Vomit Zombie update. This is a **legacy/V1 reference** and must not automatically be treated as proof that every one of those details remains unchanged in the current experience. [OFFICIAL — V1]

The current experience is presented as an 8-player game by the public catalogue Rolimon's. The same catalogue lists kill milestones, day-survival milestones, Blue Flame-related purchases and a number of premium catalogue entries. These are supporting public metadata, not a complete gameplay manual. [PUBLIC REFERENCE]

### Core identity

The experience is best described as:

- A third-person, character-following zombie survival game.
- A repeatable survival session organised around days.
- A school-centred environment with indoor and outdoor combat/exploration spaces.
- A game where the player tries to survive, defeat enemies and improve their run.
- A session with visible kill and survival counters.
- A multiplayer environment in which other player avatars can be present.
- A progression economy that includes a special currency called **Blue Flames** / **Blue Fire** in public descriptions.

The supplied video demonstrates a survival/action loop rather than a linear episode-by-episode retelling of the television series.

---

## 3. High-level player fantasy and design pillars

### 3.1 Player fantasy

The player is an ordinary student-like avatar caught in a zombie outbreak around a school. They move through familiar school spaces, encounter infected enemies, survive successive day cycles, improve their capability and attempt to last longer than other players.

### 3.2 Design pillars

1. **Readable third-person survival:** The player character remains visible, and the camera gives a clear view of nearby threats and navigation.
2. **Familiar school spaces:** Hallways, classrooms, windows, doors and exterior grounds create a recognisable school campus.
3. **Escalating survival pressure:** The passage of days is a central progress signal. The experience is designed around lasting longer.
4. **Immediate feedback:** Health, kills, survival days and currency are visible during play.
5. **Repeatable progression:** Kills and survival milestones contribute to longer-term advancement and/or the current run.
6. **Social survival:** Other avatars share the space, creating opportunities for cooperation and crowd encounters.
7. **Short readable action beats:** Players move, reposition, face enemy groups, earn progress and prepare for the next day.

---

## 4. Core gameplay loop

The main loop inferred from the official descriptions and the supplied recording is:

1. **Enter the survival environment.** The player spawns as a humanoid avatar in or near the school environment.
2. **Orient and move.** The player navigates corridors, classrooms and outdoor areas using a third-person camera.
3. **Locate threats.** Infected enemies appear in the environment and approach or engage players.
4. **Survive encounters.** The player avoids being overwhelmed while using the game's abstract combat system.
5. **Earn progress.** Defeating enemies increases the kill counter; public descriptions associate certain kill milestones and boss contributions with Blue Flame currency.
6. **Use progression interfaces.** The player can access upgrade/shop elements and improve their run or account progression.
7. **Reach the next day.** A visible countdown announces the next day; the video shows messages such as “Next day in 15 seconds!” and later “Next day in 12 seconds!”
8. **Face a harder survival phase.** The day counter and enemy pressure advance. The exact difficulty formula is unknown.
9. **Continue until defeated or the session ends.** The legacy V1 description says accumulated run progress is lost on death; whether the current experience uses exactly the same reset rules requires verification.

### 4.1 Run loop versus account progression

The reference appears to distinguish at least two progression concepts:

- **Run/session progress:** Current survival day, current kill count and current equipment/status during a run.
- **Longer-term progression:** Blue Flame currency, cosmetic options, upgrades, leaderboards or milestones.

The exact persistence rules for each item must be verified. The V1 description explicitly says that everything is lost on death, but the wording may refer to the run's temporary equipment and progress rather than every permanent account unlock.

### 4.2 Day transition

**[VIDEO]** A large on-screen message announces the next day with a seconds countdown. The video shows this in the outdoor/school sequence around 08:30–08:50 (approximate recording time; playback includes streamer overlay).

**Recreation requirement:**
- Show a clear transition announcement.
- Display a countdown.
- Preserve player control or temporarily restrict it according to observed reference behaviour; this is **[TO VERIFY]**.
- Advance the day value when the countdown completes.
- Communicate the change in difficulty and/or enemy activity.
- Avoid an unexplained hard cut: use a short transition, ambience change or spawn pacing change if that matches further reference capture.

---

## 5. World and map specification

### 5.1 Overall layout visible in the recording

The video shows a school-centred map with at least two broad environmental zones:

**A. School interior**
- Long, straight corridors with tiled or square-pattern flooring.
- Light-coloured walls.
- Repeated classroom doorways and large window panels.
- Fluorescent-style ceiling lights.
- Classroom interiors containing rows of desks and chairs.
- Wall-mounted school signage or boards.
- Hallway intersections and door openings.
- At least one long interior passage with a view toward other players/enemies.

**B. School exterior**
- Broad grassy grounds surrounding or adjacent to the school.
- Trees and planted greenery around the perimeter.
- A large school building visible from outside.
- Open space that allows players to see and move around enemy groups at a distance.
- Outdoor daylight and night/darker conditions are both visible in the recording.

**[VIDEO]** Interior hallways and classroom areas are visible at approximately 00:55–05:45 and again around 14:30–17:40. The exterior grass/school grounds are visible around 06:00–08:30 and 11:00–14:30. These times are approximate.

### 5.2 Map areas to reproduce

The following is a practical map breakdown based on what can be seen. It is a **reconstruction map plan**, not a claim that these are the exact official room names.

| Zone | Visible/required characteristics | Gameplay function |
|---|---|---|
| Main corridor | Long hallway, doors, windows, tiled floor, ceiling lights | Navigation, sightlines, enemy approach |
| Classroom A | Desk/chair rows, windows, teaching wall/board | Cover-like obstacles, enclosed encounter space |
| Classroom B / adjacent room | Similar school room language | Alternate route and encounter variation |
| Corridor junction | Intersecting hallways or doorway transitions | Route choice and ambush potential |
| School entrance / exit area | Connection between interior and exterior | Transition between close and open combat spaces |
| Front grounds | Large lawn and view of school façade | Open-area survival and group encounters |
| Tree/perimeter zone | Trees and greenery at the edge of the grounds | Visual boundary and navigation landmarks |
| Open exterior field | Broad, relatively unobstructed grass | Large groups and long-distance visibility |

### 5.3 Spatial design principles

To match the recording:
- Corridors should be long enough to create visible approach distance.
- Classroom doors should open into recognisable room volumes, not decorative flat facades.
- Classroom furniture should be arranged in repeated rows with walkable aisles.
- Windows should make the school feel connected to the exterior.
- The school should remain visually legible from outside.
- Exterior space should be substantially more open than the interior.
- Trees and the perimeter should frame the play area without obscuring navigation.
- Use repeated modular school architecture, but add enough variation in room dressing to avoid a copy-pasted appearance.

### 5.4 What is not yet established

The supplied video does **not** provide enough evidence to accurately reconstruct:
- Every floor of the school.
- A complete room-by-room floor plan.
- Exact corridor dimensions.
- Whether all doors are enterable.
- Exact spawn points and enemy navigation routes.
- Whether there are hidden rooms, rooftops, basements, gymnasiums, laboratories or other areas.
- Exact boundaries of the playable map.

These details must be captured in a later map survey. Do not invent them as confirmed features.

---

## 6. Camera and player movement

### 6.1 Camera perspective

**[VIDEO]** The recording uses a third-person follow camera. The player avatar is visible from behind and occupies the lower-central region of the gameplay view. The camera follows as the avatar moves through corridors and across the outdoor field.

**Recreation target:**
- Third-person camera positioned behind and slightly above the character.
- Character remains visible during ordinary movement.
- Camera follows smoothly rather than snapping on every small direction change.
- Camera framing leaves enough forward view to read the corridor and see approaching enemies.
- Camera should avoid clipping through walls and classroom geometry.
- Camera behaviour in narrow corridors should preserve visibility of the player and immediate surroundings.

### 6.2 Movement states

The recording clearly shows continuous ground movement and direction changes. The precise input mapping and all movement states are not visible, so the following separates confirmed movement from implementation assumptions.

| Movement state | Evidence status | Recreation behaviour |
|---|---|---|
| Idle / standing | **[VIDEO]** | Character can remain stationary while the camera follows |
| Forward movement | **[VIDEO]** | Character advances through corridors and across grass |
| Turning / directional change | **[VIDEO]** | Character changes heading to navigate rooms and face activity |
| Jog/run-like locomotion | **[VIDEO / TO VERIFY exact speed]** | Use a clear locomotion cycle consistent with the pace shown |
| Backward movement | **[TO VERIFY]** | Do not assume exact availability or speed |
| Strafing | **[TO VERIFY]** | Confirm whether movement direction is camera-relative |
| Sprint | **[TO VERIFY]** | No sprint input or stamina bar is conclusively established by this recording |
| Jump | **[TO VERIFY]** | Not enough evidence to define jump height, air control or cooldown |
| Crouch / stealth | **[TO VERIFY]** | Not established by the recording |
| Climb / vault | **[TO VERIFY]** | Not established by the recording |
| Dodge / roll | **[TO VERIFY]** | Not established by the recording |

### 6.3 Character animation requirements

The standalone character should support:
- Idle breathing/weight-shift animation.
- Forward locomotion.
- Directional turning.
- Start/stop transitions.
- A stable upper-body pose during locomotion.
- Context-appropriate hit reaction and defeat animation.
- Interaction pose if the reference later confirms an interaction system.

The animation style should reflect the reference's stylised Roblox-like proportions rather than defaulting to realistic cinematic human proportions. The target is a faithful *feel*, not an unrelated photorealistic redesign.

### 6.4 Collision and movement feel

- The player should not pass through walls, desks or closed geometry.
- Classroom furniture should shape routes without making every aisle frustratingly narrow.
- Corridors should allow the player to pass other avatars and enemies.
- Camera collision should be handled separately from character collision.
- Movement should feel responsive, with no unnecessary acceleration delay.
- Any movement speed values must be measured from reference gameplay before being treated as final.

---

## 7. Player avatar and character presentation

### 7.1 Player character

The player is represented by a stylised humanoid avatar. The supplied recording shows different avatar appearances across the session, indicating that the experience does not require every player to use one fixed protagonist model.

**Recreation requirements:**
- Support a customisable or selectable avatar appearance.
- Preserve a readable silhouette from the third-person camera.
- Separate the character body, clothing and cosmetic appearance from the movement/combat controller.
- Allow other players to be visually distinct at a glance.
- Keep animation and hit feedback readable at a distance.

### 7.2 Character identity

The supplied video does not establish a fixed story protagonist or a canonical playable cast. It shows player-controlled avatars rather than a scripted roster of named television characters.

**Do not assume** that On-jo, Cheong-san, Nam-ra or other television characters are playable characters in this Ranimated survival experience unless a separate reference confirms it.

### 7.3 Character states

The standalone implementation should at minimum model these game states:
- Alive and controllable.
- Taking damage / hit reaction.
- Defeated / dead.
- Respawned or returned to a new session, if confirmed by reference testing.
- In a menu/shop interface.
- Temporarily waiting during a day transition, if the original restricts control then.

Infection as a player state is **not confirmed** by the supplied current-game recording. The older V1 description references zombie-related planned updates, but that is not sufficient to claim that the current experience supports player infection.

---

## 8. Enemy / infected design

### 8.1 Basic infected

**[VIDEO]** The video shows multiple hostile humanoid figures in school corridors and on the outdoor grounds. They gather around players and create pressure through numbers.

Recreation requirements:
- Infected are recognisable as hostile NPCs.
- They can navigate the environment.
- They detect or engage players within a defined awareness range.
- They approach the player and create an immediate survival threat.
- Their group behaviour should create pressure without making navigation impossible.
- They should be visually distinguishable from player avatars.

### 8.2 Enemy behaviour model

A useful implementation model (not a confirmed description of the original's internal AI) is:

1. **Dormant / roaming:** Enemy is present in the world and follows a simple patrol or idle behaviour.
2. **Alerted:** Enemy detects a nearby player or receives an alert from another enemy.
3. **Approach:** Enemy moves toward the target using navigation.
4. **Engagement:** Enemy attempts its game-defined close-range attack/contact behaviour.
5. **Recovery:** Enemy returns to movement after an action.
6. **Defeated:** Enemy is removed or enters a defeat state, and the game updates the relevant counters/rewards.

### 8.3 Group behaviour

The video shows groups rather than only isolated enemies. The recreation should support:
- Several enemies pursuing the same player.
- Enemies approaching from different directions.
- Enemy spacing that prevents all units occupying the same point.
- Pathfinding around desks, walls and doorframes.
- A sensible cap on active enemies to preserve performance.
- Spawn pacing that scales with the survival day.

### 8.4 Special enemy references

The **V1** Roblox description lists a Blood Moon event and a Vomit Zombie update. A third-party Roblox wiki page for the V1 experience also mentions a Boss and Cone Boss in relation to Blue Fire rewards. These are historical references and may not describe the current experience exactly.

For the standalone recreation, treat these as candidate special enemy/event types pending confirmation:
- Standard infected.
- A tougher boss-class infected.
- A special event enemy associated with a Blood Moon or similar event.
- A ranged/area-pressure special infected, if the historical “Vomit Zombie” is confirmed in the intended version.

Do not lock their exact attacks, health, movement speed, spawn rate or rewards until further gameplay footage is available.

---

## 9. Combat and encounter structure

The video establishes that combat is a central part of the survival loop: the kill counter rises significantly during the recording, and players engage groups of infected in both indoor and outdoor spaces.

This document intentionally specifies combat at the **game-system level** rather than as real-world weapon instruction.

### 9.1 Combat requirements

- Player can engage hostile infected through the game's abstract combat interface.
- Enemy defeat produces immediate visual and UI feedback.
- Kill count updates reliably.
- Combat remains readable in third-person view.
- Multiple enemies can be present simultaneously.
- Combat can take place in corridors, classrooms and open exterior spaces.
- The system should support progression-linked equipment or capability tiers, as described by the public game references.

### 9.2 Feedback

Required feedback:
- Clear indication that an enemy has been hit or defeated.
- A kill counter update.
- A clear player damage/health response.
- Distinct audio cues for encounter start, hit confirmation, enemy defeat and day transition.
- No excessive screen effects that obscure nearby threats.

### 9.3 Combat details requiring confirmation

The recording alone does not establish exact:
- Damage values.
- Enemy health values.
- Attack cadence.
- Reload or resource rules.
- Equipment statistics.
- Aim assistance or targeting rules.
- Whether damage is server-authoritative.
- Whether all enemy types use the same damage model.

These should be measured from additional controlled gameplay rather than guessed.

---

## 10. Health, defeat and survival

### 10.1 Health display

**[VIDEO]** The lower-left HUD shows a green health bar and a numeric display reading **100/100** in the sampled gameplay. The bar is a prominent, easy-to-read status element.

Recreation requirements:
- Show current and maximum health.
- Use a horizontal bar with a numeric value.
- Update immediately when the player receives damage or recovers.
- Make critical health visually distinct without relying only on colour.
- Keep the health display anchored consistently to the lower-left HUD region.

### 10.2 Defeat and run loss

The V1 experience description explicitly says the player loses everything on death. This supports a run-loss model for the legacy version. The current game's exact reset rules remain **[TO VERIFY]**.

For the standalone recreation, implement the rule as a configurable design setting until the intended version is verified:
- Which run-specific items reset?
- Does the day counter reset?
- Does the run kill count reset?
- Which permanent currency remains?
- Are cosmetics retained?
- Is there a revive or continue option?

Do not silently decide these rules; they materially affect the game's progression loop.

---

## 11. HUD and interface specification

The interface is one of the most important parts of the supplied video. It remains visible during movement and combat.

### 11.1 Visible HUD layout

| Screen region | Visible element | Evidence |
|---|---|---|
| Upper-right | Kill count | **[VIDEO]** |
| Upper-right | Days survived / day status | **[VIDEO]** |
| Right edge | Blue Flame / Blue Fire currency indicator | **[VIDEO + PUBLIC REFERENCE]** |
| Right edge | Upgrade-related button or shortcut | **[VIDEO]** |
| Lower-left | Health bar and numeric health | **[VIDEO]** |
| Bottom-centre | Several circular/slot-like icons | **[VIDEO]**, exact functions unverified |
| Centre / world | Day-transition announcement and countdown | **[VIDEO]** |
| Menus / world panels | Shop and leaderboard-like boards | **[VIDEO]**, exact navigation behaviour unverified |

### 11.2 Kill and day counters

- Kill counter is displayed prominently near the top-right.
- The value rises as enemies are defeated.
- Day survival status is displayed nearby.
- These are the primary at-a-glance progression indicators.
- Both must remain readable during combat and outdoor movement.

### 11.3 Blue Flame currency

The public description of the older V1 game calls the currency “Blue flames”; the current public catalogue also lists Blue Flame-related purchases. The recording shows a blue flame-like currency indicator on the right side of the HUD.

The public Roblox wiki says Blue Fire can be earned through contributions to boss kills, killing ten enemies, or purchased with Robux in the V1 experience. Because this is a third-party description of V1, the exact current earning rules need verification.

### 11.4 Upgrade and shop interface

The recording shows an upgrade affordance on the right side and a shop-like area/board in the environment. The precise menu contents and upgrade tree are not legible enough to document reliably.

Recreation requirements:
- A clearly accessible upgrade/shop screen.
- Currency balance visible.
- Item/upgrade entries with cost and current status.
- Purchase confirmation and clear feedback.
- Distinction between permanent unlocks and temporary run upgrades, once verified.
- No fabricated prices or upgrade statistics.

### 11.5 Bottom action icons

Several small circular icons are visible along the lower centre of the gameplay HUD. Their exact functions cannot be confidently identified from the recording. They may represent equipment, abilities, inventory slots or shortcuts.

**[TO VERIFY]** Capture a high-resolution screenshot and test each icon before assigning functionality.

---

## 12. Progression and economy

### 12.1 Survival-day progression

The day count is a central game objective. The V1 description explicitly says the player survives as many days as possible and that new equipment unlocks after each day. The current recording visibly shows day-transition countdowns.

### 12.2 Kill progression

The kill counter is persistent on the HUD during the run. The video shows the count increasing from low values early in the recording to several hundred later. Public metadata also lists kill milestone achievements such as 100, 1,000, 10,000 and 100,000 kills.

### 12.3 Blue Flame economy

Public references connect Blue Flame/Blue Fire to:
- Progression rewards.
- Boss-related contribution rewards in the V1 wiki description.
- Kill-based reward thresholds in the V1 wiki description.
- Purchases and premium catalogue entries in third-party catalogue data.

The standalone design should keep the currency system data-driven. Do not hardcode unverified earning rates or prices.

### 12.4 Leaderboards and achievements

The public catalogue lists kill and day-survival milestones. The supplied recording also shows leaderboard-like presentation. These support the following recreation goals:
- Track best survival day.
- Track total or session kills, depending on the reference's distinction.
- Display milestone achievements.
- Provide a leaderboard presentation for competitive comparison.
- Keep session counters separate from lifetime statistics.

Whether the original has local, global, daily or server-only leaderboards requires verification.

---

## 13. Multiplayer and social presentation

The current public catalogue lists a maximum server size of eight players. The video shows multiple player avatars in the same environment.

### Multiplayer requirements

- Multiple human-controlled avatars share the same school map.
- Players can be seen moving through the same spaces.
- Enemy encounters can involve several players.
- The UI and world must remain readable when several avatars are nearby.
- Player appearance should distinguish one participant from another.
- The game should remain playable when players are spread across interior and exterior areas.

### Network behaviour to verify

- Whether kill credit is awarded to the last player to damage an enemy or shared.
- Whether Blue Flame rewards are shared.
- Whether players can revive one another.
- Whether player collision is enabled.
- Whether the day timer is global to the server.
- What happens when a player joins mid-session.
- Whether a player can leave and rejoin the same run.

These are not settled by the supplied recording.

---

## 14. Lighting, atmosphere and audio

### 14.1 Visual atmosphere

The video shows:
- Cool, grey school corridors.
- Bright fluorescent-style interior lighting.
- Warm-toned classroom floors and furniture.
- A green outdoor lawn.
- Trees and a visible school exterior.
- Outdoor sequences in both brighter daylight and darker/night-like conditions.
- A slightly foggy or softened distance in some exterior/interior views.

### 14.2 Lighting requirements

- Interior lighting should feel institutional and slightly cold.
- Classrooms should be warmer and more visually varied than corridors.
- Outdoor lighting should clearly communicate time-of-day changes.
- Night/dark phases should remain playable and navigable.
- Enemy silhouettes should remain visible against the environment.
- Fog should support depth and atmosphere without hiding important threats.

### 14.3 Audio

The supplied recording includes a creator/streamer voice overlay, so it is not a clean source for the game's original audio. The game's exact soundtrack, ambient loops and sound effects cannot be reliably separated from commentary.

Audio elements to capture in a later reference pass:
- School ambience.
- Outdoor ambience.
- Enemy vocalisations.
- Movement/footstep sounds.
- Combat feedback.
- UI interactions.
- Day-transition cue.
- Event/boss cue.
- Music changes between survival phases.

Do not treat the streamer's microphone audio as part of the game.

---

## 15. Session pacing and difficulty

The recording shows the player progressing from a low kill count to hundreds of kills over the session. The outdoor sections show large groups and a more open encounter space. This suggests the game is designed for repeated enemy engagements and escalating survival pressure.

### Reconstruction model

A configurable day-based director should control:
- Enemy population.
- Spawn interval.
- Enemy mix.
- Special-event chance.
- Transition countdown.
- Any day-specific reward or unlock.

The exact values must be calibrated from gameplay tests. No enemy counts, spawn intervals or scaling multipliers are confirmed by the sources currently available.

### Pacing goals

- Early session: teach the space and establish the survival loop.
- Middle session: increase pressure and encourage movement between areas.
- Later session: create larger, more demanding encounters.
- Day transition: provide a short readable break and a clear progress signal.
- Special event: visibly distinguish it from an ordinary day if Blood Moon-style events are part of the chosen version.

This is a reconstruction proposal, not a confirmed description of the original's internal difficulty algorithm.

---

## 16. Timestamped video observation log

The following timestamps refer to the supplied recording and are approximate. The recording contains a streamer face-camera overlay and browser/intro material before the gameplay begins.

| Approx. recording time | Observation |
|---|---|
| 00:00–00:30 | Intro/browser view and streamer overlay before sustained gameplay |
| 00:30–01:30 | Third-person avatar appears in a school corridor; other avatars/enemies visible ahead |
| 01:30–03:30 | Continued corridor navigation and encounters; kill counter visible |
| 03:30–05:30 | Classroom interior with desk rows; player moves between school spaces |
| 05:30–06:30 | Return to corridor / school interior |
| 06:30–08:30 | Outdoor grassy grounds and school exterior; multiple characters/enemies visible |
| 08:30–09:00 | Day transition countdown message appears |
| 09:00–10:30 | Return to school corridor and interior activity |
| 10:30–11:30 | Shop/upgrade/leaderboard-like presentation visible |
| 11:30–14:30 | Outdoor survival sequences; player engages groups in the grass |
| 14:30–16:00 | Return to school interior and corridor encounters |
| 16:00–17:30 | More close corridor encounters and several player avatars together |
| 17:30–18:23 | Gameplay continues; shop/board area and closing streamer overlay |

The exact timestamps should be rechecked against the original video player if frame-accurate documentation is needed.

---

## 17. Character and movement implementation checklist

### Player controller
- [ ] Third-person follow camera.
- [ ] Camera smoothing and collision.
- [ ] Responsive ground movement.
- [ ] Idle and locomotion animation.
- [ ] Directional turning.
- [ ] Collision with school geometry.
- [ ] Health state.
- [ ] Defeat state.
- [ ] Multiplayer avatar replication.
- [ ] Customisable appearance or avatar selection.

### Infected AI
- [ ] Navigation through corridors.
- [ ] Navigation around classroom furniture.
- [ ] Player detection.
- [ ] Target selection.
- [ ] Group pursuit.
- [ ] Attack/contact state.
- [ ] Hit reaction.
- [ ] Defeat state.
- [ ] Kill counter integration.
- [ ] Day-based spawn director.
- [ ] Special enemy/event framework.

### World
- [ ] Main school corridor.
- [ ] Classroom with desk rows.
- [ ] Additional classroom/room variant.
- [ ] Corridor junctions.
- [ ] School entrance/exit transition.
- [ ] Exterior lawn.
- [ ] Trees/perimeter.
- [ ] School façade.
- [ ] Day/night lighting variation.

### UI and progression
- [ ] Health bar and numeric value.
- [ ] Kill counter.
- [ ] Day-survival counter.
- [ ] Day transition countdown.
- [ ] Blue Flame currency display.
- [ ] Upgrade/shop interface.
- [ ] Bottom action/inventory icons (after verification).
- [ ] Leaderboard/statistics display.
- [ ] Kill and day milestone tracking.
- [ ] Run-vs-permanent progression separation.

---

## 18. Unresolved questions and next reference-capture pass

The current recording is a strong overview but not sufficient to reproduce every detail exactly. A second capture pass should deliberately inspect:

1. Main menu, loading screen and spawn sequence.
2. Full HUD at high resolution.
3. Every bottom-centre icon and right-side button.
4. Shop and upgrade pages, including all visible categories and descriptions.
5. Exact player movement states and controls.
6. Player damage, health loss and defeat behaviour.
7. Enemy detection and movement in a controlled encounter.
8. All visible infected variants.
9. Boss/special event behaviour, if present in the current version.
10. Day transition timing and what changes when a new day begins.
11. Death and respawn/reset rules.
12. Full school map route survey, including all accessible rooms and floors.
13. Multiplayer join/leave behaviour.
14. Audio and music without streamer commentary.
15. Whether current-game mechanics differ from the older V1 description.

### Important version-control rule

Keep two reference profiles in the project:
- **Current Ranimated experience — ID 9759729519:** primary target for this recreation.
- **Ranimated V1 — ID 8694898220:** historical reference only.

A feature documented for V1 should not be merged into the current target until confirmed. This prevents the recreation from accidentally combining different versions.

---

## 19. Reference sources

### Primary source: supplied gameplay recording

- User-provided file: `YTDown.com_YouTube_Media_axjbAZ8P8l8_Roblox-All-of-Us-Are-Dead_003_480p.mp4`
- Duration: approximately 18 minutes 23 seconds.
- Used for: third-person camera, visible player avatars, school corridors, classroom layout, outdoor grounds, health display, kill/day counters, Blue Flame-style currency indicator, day countdown, shop/upgrade-like presentation and encounter pacing.
- Note: streamer face-camera and commentary are not part of the game.

### Official Roblox experience pages

1. **Ranimated — All of Us Are Dead** (current target; experience ID 9759729519)  
   https://www.roblox.com/games/9759729519/All-of-Us-Are-Dead  
   The page identifies Ranimated as creator and describes the experience as a zombie game based on the Korean series.

2. **Ranimated — All of Us Are Dead V1** (historical reference; experience ID 8694898220)  
   https://www.roblox.com/games/8694898220/All-of-Us-Are-Dead-V1  
   Its description documents the survive-as-many-days loop, day-based unlocks, loss of run progress on death, Blood Moon event and Vomit Zombie update.

### Public secondary references

3. **Roblox Wiki — Ranimated / All of Us Are Dead**  
   https://roblox.fandom.com/wiki/Ranimated/All_of_Us_Are_Dead  
   Secondary reference for the V1 description, survival objective, Blue Fire earning notes and historical enemy/event references. Community-edited; verify against the game.

4. **Rolimon's — All of Us Are Dead (experience ID 9759729519)**  
   https://www.rolimons.com/game/9759729519  
   Secondary catalogue reference for creator attribution, server size, public statistics, kill/day milestones and catalogue entries. Not a full mechanics guide.

5. **Rolimon's — All of Us Are Dead V1 (experience ID 8694898220)**  
   https://www.rolimons.com/game/8694898220  
   Secondary catalogue reference for the older V1 experience and its historical description.

6. **Ranimated experience listing on Roblox**  
   https://www.roblox.com/games/9759729519/All-of-Us-Are-Dead  
   Use the live creator page as the first stop when checking whether an item has changed in a newer update.

---

## 20. Final target definition

The standalone recreation should be judged against the following baseline:

> A stylised third-person multiplayer zombie-survival game set around a school campus. The player controls a visible humanoid avatar, navigates school corridors and classrooms, moves out into broad grassy grounds, survives groups of infected, tracks kills and survival days, uses a Blue Flame-style progression economy, accesses upgrades/shop systems, and faces successive day-based survival phases with increasing pressure.

The first development milestone should reproduce one complete playable loop:
1. Spawn into the school environment.
2. Move through a corridor and classroom.
3. Encounter a group of infected.
4. Survive and receive kill/health feedback.
5. Reach a day-transition countdown.
6. Advance to the next survival day.
7. Access the progression/shop interface.

Only after this loop feels right should the project expand to the full map, all enemy variants, complete progression, multiplayer polish and detailed cosmetic systems.

**Accuracy principle:** Reproduce what can be observed and verified. Mark unknowns rather than inventing them. Use the supplied recording as the primary visual/gameplay reference and the official current Roblox page as the primary version identity reference.
