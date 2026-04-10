# Transcendence - Online Board Game (Concept)

## 1) Overview

Online multiplayer game concept with fishing ships and light pirate-style conflict.

- Inspiration: a mix of Quartz + King of Tokyo.
- Players: 6 to 8 players per match.
- Objective: finish the game with the most money earned from selling fish.
- Core decision axis: risk vs reward between safer seas and more dangerous seas.

## 2) Map and seas

The board has 5 seas:

- 1 central sea (calmer).
- 4 outer seas around the center.

Difficulty rule (clockwise from the top-right corner):

1. Outer Sea A (easiest)
2. Outer Sea B
3. Outer Sea C
4. Outer Sea D (hardest)

As difficulty increases:

- environmental danger increases,
- average fishing quality/value increases,
- chance of negative events increases.

## 3) Capacity per sea

Each sea has a ship limit. If a sea is full and someone tries to enter, a battle occurs.

Suggested capacity for balancing (can be adjusted in playtests):

- Central Sea: 4 slots
- Outer A: 2 slots
- Outer B: 2 slots
- Outer C: 2 slots
- Outer D: 2 slots

## 4) Win condition

- Match lasts a fixed number of rounds (suggestion: 10 to 14).
- At the end, the player with the most coins wins.
- Tiebreakers:
1. Highest value of completed fish sets.
2. Highest number of sold rare fish.
3. Highest remaining HP.

## 5) Turn structure

Each round has the following phases:

1. Planning Phase
- Player chooses 1 main action (or more if cards allow it).

2. Movement Phase
- Player may attempt to change seas.
- If the target sea is full, an occupation battle starts.

3. Action Phase
- Player uses active cards/effects.
- Offensive, defensive, or economic actions.

4. Environmental Hazard Phase
- Each player in a sea resolves that sea's hazard.

5. Fishing Phase (mandatory)
- Every player must fish at the end of the turn.
- Quantity and quality depend on sea and active buffs/debuffs.

6. Market Phase
- Player may sell part or all of cargo.
- Fish sets grant sale bonuses.

## 6) Available actions before ending the round

Base action list per turn (1 main action by default):

- Move to another sea.
- Repair hull (recover health).
- Fortify ship (temporary defense).
- Plunder target (steal 1 random fish with failure chance).
- Play attack/defense/utility card.
- Trade (sell with a small bonus in favorable market).

## 7) Combat system

Combat occurs when:

- a player tries to enter a full sea,
- a card or skill creates direct conflict.

Suggested format for fast online combat:

- Each side rolls 1d6 + ship attack + card modifiers.
- Loser takes damage equal to the difference (minimum 1).
- Best of 3 exchanges, or until one side yields.

Result in slot disputes:

- Winner takes the slot in the contested sea.
- Loser retreats to a valid adjacent sea.
- If there is no valid sea, loser is moved to the central sea.

## 8) Health, damage, and elimination

Suggested base health per ship:

- Starting HP: 10

Damage sources:

- Ship combat.
- Sea hazards.
- Certain cards/events.

When HP reaches 0:

- Ship sinks.
- Player loses part of cargo (suggestion: 50% random fish).
- Player returns next turn to Central Sea with partial HP (suggestion: 6).

Design note:

- Avoiding permanent elimination improves online experience (nobody sits out too long).
- Optional hardcore mode can allow permanent death.

## 9) Fishing and economy

Fish types (initial example):

- Common: Sardine, Anchovy
- Uncommon: Tuna, Mackerel
- Rare: Swordfish, Blue Salmon
- Epic: Golden Sunfish

Simple sea table (example):

- Central Sea: high common chance, low uncommon chance
- Outer A: common + uncommon
- Outer B: stable uncommon, low rare
- Outer C: medium rare, high risk
- Outer D: high rare, epic chance, very high risk

Selling:

- Sold fish generate immediate coins.
- Holding fish for set completion can give higher value later.

## 10) Fish sets (set collection)

Suggested sets:

- Local School: 3 different common fish -> fixed sale bonus.
- Export Batch: 2 uncommon + 1 rare -> high bonus.
- Ocean Trophy: 2 rare + 1 epic -> very high bonus.

Set rules:

- Set can be sold at any time in Market Phase.
- Selling a set consumes all fish used by that set.

## 11) Action cards

Initial deck with quick-resolution cards:

- Extra Attack: +1 attack this round.
- Heavy Cannon: +2 in one combat exchange.
- Smoke Screen: ignore 1 incoming attack.
- Reinforced Hull: ignore environmental damage this round.
- Opportunistic Theft: steal 1 random fish from a target in the same sea.
- Special Net: +1 fish during mandatory fishing.
- Evasive Maneuver: cancel one plunder attempt against you.

Card rules:

- Suggested max hand size: 3 cards.
- Suggested draw rate: 1 card every 2 rounds, or via event.
- Per-turn limit: 1 card (unless a special effect says otherwise).

## 12) Sea hazards

Each outer sea has a risk table. Example:

- Outer A: 20% chance to take 1 damage.
- Outer B: 30% chance to take 1 damage.
- Outer C: 40% chance to take 1-2 damage.
- Outer D: 50% chance to take 2 damage.

Hazards may include:

- Storm.
- Hidden rocks.
- Strong current.
- Sea monster.

## 13) Synchronization rules for the online version

Because it is online, use a server-authoritative model:

- Server validates all gameplay actions.
- Client only sends intent (desired action).
- Final state is always decided by server.

Suggested real-time (WebSocket) events:

- lobby:update
- game:start
- turn:begin
- player:move
- combat:start
- combat:result
- hazard:result
- fishing:result
- market:sell
- card:played
- player:sunk
- game:end

Robustness requirements:

- Reconnection with state recovery.
- Turn timeout to prevent match stalls.
- Event log for auditing and simple replay.

## 14) Match flow (high-level)

1. Lobby
- Room creation.
- 6 to 8 players join.
- Configuration choice (round count, normal/hardcore mode, optional seed).

2. Setup
- Initial ship distribution.
- Initial placement in central sea.
- Optional starting cards.

3. Rounds
- Execute turn phases for all players.
- Update partial ranking by coins.

4. Endgame
- Final fish sale.
- Set bonuses.
- Tiebreakers.
- Final screen with ranking and statistics.

## 14.1) Quick mode for evaluation

Mode designed for short matches and easier in-class testing.

Mode goals:

- reduce total match duration;
- preserve risk vs reward;
- simplify cards and decisions;
- remove direct player-vs-player combat.

Main rules:

- 4 to 6 rounds;
- no hard limit of ships per sea;
- player contention happens indirectly through crowding pressure in the same sea;
- action cards are simpler and have immediate effects.

Sea crowding hazard:

- each sea has its base hazard;
- each extra player in the same sea increases hazard;
- simple suggestion: for each ship above the first in the same sea, everyone there receives +1 damage or +1 on hazard test;
- this increase can have a cap to avoid extremes, for example +3 max;
- this makes crowded seas riskier even without direct combat.

Simplified turn structure:

1. Movement
- player chooses a destination sea;
- player may move or stay;
- crowded seas do not block entry.

2. Sea hazard
- apply base hazard from that sea;
- apply crowding bonus based on number of ships present.

3. Mandatory fishing
- every player fishes at end of turn;
- more dangerous seas offer better fishing with more risk.

4. Market
- player may sell fish or hold them for sets.

Simplified cards:

- Quick Movement: move with no extra cost.
- Light Repair: recover 1 or 2 health.
- Naval Shield: ignore 1 damage this turn.
- Improved Net: gain +1 fish while fishing.
- Favorable Sale: sell with a small bonus.

What this mode gains:

- shorter matches;
- fewer rules to explain;
- less downtime;
- stronger focus on positioning and environmental risk.

What this mode loses:

- less direct confrontation;
- less player-driven unpredictability;
- less tactical depth from combat.

Provisional conclusion:

- for project evaluation, this quick mode appears to be a good choice;
- it preserves game identity and shortens match time without removing the key decision between safer and riskier seas.

## 14.2) How to support both modes without duplicating work

Best strategy: share one game core and change only parameters and a few mode-specific rules.

Shared base for both modes:

- same match structure;
- same seas and fishing system;
- same coin economy and fish selling;
- same card system, with different card lists by mode;
- same server turn model.

Differences by configuration:

- number of rounds;
- presence or absence of ship limits per sea;
- environmental hazard intensity;
- presence or absence of direct combat;
- card quantity and complexity.

Practical organization:

- quick mode can be the default evaluation mode;
- normal mode reuses the same phases with richer rules;
- whenever possible, logic should come from a configuration such as mode = quick or mode = full;
- this avoids building two separate games.

Benefits of this approach:

- less duplicated code;
- lower bug risk;
- simpler balancing;
- easier demonstration without abandoning the complete-mode vision.

## 15) Useful metrics and statistics

For match history and player profile:

- Total coins per match.
- Fish caught by rarity.
- Completed sets.
- Damage dealt/taken.
- Number of times sunk.
- Win rate.
- Most visited sea.

## 16) MVP prototype focus

Minimum playable scope (MVP):

- Lobby for 6-8 players.
- 5 seas with limits.
- Movement + slot dispute via combat.
- Environmental damage.
- Mandatory fishing at end of each turn.
- Fish selling and coin-based scoring.
- 10 basic cards.
- Endgame ranking screen.

Iteration 2 items:

- Economy fine-tuning.
- More card types.
- Detailed match history.
- Spectator mode.

## 17) Open decisions to align as a team

- Exact number of rounds.
- Final damage values by sea.
- Rarity curve by zone.
- Initial card count per player.
- Final sinking rule (respawn vs elimination).
- Desired randomness level (more strategy vs more chaos).

## 18) Temporary game name

Suggested internal codename:

- Five Seas: Fisher Clash

Can be changed later with no technical impact.
