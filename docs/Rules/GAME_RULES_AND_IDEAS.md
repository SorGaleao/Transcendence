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

## 3) Occupation rule

Only one ship may occupy each outer sea at a time.

The lagoon is a shared safe hub:

- it can contain multiple ships;
- it is the only place where fish can be sold;
- defeated players always return there.

Occupancy rule:

- If an outer sea is free, the player may enter it.
- If an outer sea is occupied, the incoming player must challenge the occupant in a battle.
- The loser of the battle always returns to the lagoon.
- The winner stays in the target sea.

The lagoon remains the central safe zone, the default return point after defeat, and the only shared market zone.

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
- Player may move once to any sea.
- If the target sea is free, the player enters it.
- If the target sea is occupied, an occupation battle starts.
- The loser returns to the lagoon.

3. Action Phase
- Player uses active cards/effects.
- Offensive, defensive, or economic actions.

4. Environmental Hazard Phase
- Each player in a sea resolves that sea's hazard.

5. Fishing Phase (mandatory)
- Every player must fish at the end of the turn.
- Quantity and quality depend on sea and active buffs/debuffs.

6. Market Phase
- Player may sell part or all of cargo only while in the lagoon.
- Fish sets grant sale bonuses.

## 6) Available actions before ending the round

Base action list per turn (1 main action by default):

- Move to another sea.
- Repair hull (recover health).
- Fortify ship (temporary defense).
- Play attack/defense/utility card.
- Trade (sell with a small bonus in favorable market).

## 7) Combat system

Combat occurs when:

- a player tries to enter an occupied sea,
- a card or skill creates direct conflict.

Suggested format for fast online combat:

- Each side rolls 1d6 + ship attack + card modifiers.
- Loser takes damage equal to the difference (minimum 1).
- Best of 3 exchanges, or until one side yields.

Result in occupation disputes:

- Winner takes the contested sea.
- Loser always returns to the lagoon.
- If the attacker loses, the defender keeps the sea.
- If the defender loses, the attacker occupies the sea.

## 8) Health, damage, and elimination

Suggested base health per ship:

- Starting HP: 10

Damage sources:

- Ship combat.
- Sea hazards.
- Certain cards/events.

When HP reaches 0:

- Ship sinks.
- Player loses all fish cargo.
- Player loses a percentage of gold (suggestion: 25% to 40%, rounded down).
- Player returns next turn to the lagoon with partial HP (suggestion: 6).

Repair note:

- The lagoon includes a repair dock.
- Players can pay gold to restore HP there.
- Repair should only be possible in the lagoon.

Design note:

- Avoiding permanent elimination improves online experience (nobody sits out too long).
- Optional hardcore mode can allow permanent death.

## 9) Fishing and economy

Fish types (initial example):

- Common: Sardine, Anchovy
- Uncommon: Tuna, Mackerel

### Direct theft and pressure

- Random Theft: steal 1 random fish from a player of your choice.
- Targeted Theft: steal 1 specific fish from a player of your choice, if they have it.
- Tide Purge: choose one fish type; all players, including you, discard all fish of that type.
- Shared Tide: choose one player; for 1 round, that player mirrors the fish and environmental damage you receive during your turn, without changing sea occupancy.
- Rare: Swordfish, Blue Salmon
- Epic: Golden Sunfish

Simple sea table (example):

- Central Sea: high common chance, low uncommon chance
- Outer A: common + uncommon
- Outer B: stable uncommon, low rare
- Outer C: medium rare, high risk
- Outer D: high rare, epic chance, very high risk

Selling:

- Fish can only be sold in the lagoon.
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

Initial deck with Florianopolis-themed cards (events on hold):

- Witches of the Lagoon: gain +1 in the next battle you fight this round.
- South Wind: if you defend a sea, the attacker gets -1 in the first combat exchange.
- Conceicao Mist: cancel one attack targeting you this turn.
- Channel Passage: move to any sea this turn and immediately challenge the occupant if the sea is already taken.
- Naufragados Wreck: gain +2 in one combat exchange in Outer D only.
- Tainha Season: +1 fish in mandatory fishing this turn.
- Fisherman's Blessing: heal 2 HP.
- Net of the Rendeiras: convert 1 common fish into 1 uncommon fish.
- Wharf Bargain: +20% sale value in this Market Phase.
- Hidden Current: if you win a battle, the loser returns to the lagoon and loses 1 additional fish.
- Lantern of the Watchman: ignore environmental damage this turn.
- Tide of the Island: the next player who challenges your sea takes +1 damage from the battle, and you gain 1 coin.

Card rules:

- Suggested max hand size: 3 cards.
- Suggested draw rate: 1 card every 2 rounds.
- Per-turn limit: 1 card (unless a special effect says otherwise).

Design constraints for cards:

- Keep card text short and deterministic for multiplayer sync.
- Prioritize map positioning, fishing, and economy over pure damage.
- At least 60% of cards should be useful in both quick mode and normal mode.

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
- Movement + occupation dispute via combat.
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
