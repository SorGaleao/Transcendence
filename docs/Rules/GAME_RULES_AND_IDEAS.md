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

- Match lasts 5 rounds by default (target match length: 30-40 minutes).
- Optional extended mode can use 6 rounds if turn timers stay strict.
- At the end, the player with the most coins wins.
- Tiebreakers:
1. Highest value of completed fish sets.
2. Highest number of sold rare fish.
3. Highest remaining HP.

## 5) Turn structure

Each round has the following 5 phases:

1. Optional Trading and Market
- Players may negotiate with any player regardless of location.
- Fish can be sold only if the player is currently in the lagoon.

2. Action Cards
- Player may play action cards according to hand and turn limits.

3. Movement and Battles
- Player may move once to any sea.
- If the target sea is free, the player enters it.
- If the target sea is occupied, an occupation battle starts.
- The loser returns to the lagoon.
- If the player moves to an occupied sea, battle is mandatory.
- If the player moves to a free outer sea, they may fortify defenses.
- If the player moves to the lagoon, they may repair by paying gold or do nothing.

4. Mandatory Fishing
- Every player must fish at the end of the turn.
- Quantity and quality depend on sea and active effects.

5. Reward/Consequence Cards
- Resolve cards that trigger after fishing or after battle outcomes.
- Example cards in this phase: Naufragados Wreck, Hidden Current.

## 6) Combat system

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

## 7) Health, damage, and elimination

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

## 8) Fishing and economy

Fish roster (V1):

- Common:
	- Sardine (Sardinha - Sardinella brasiliensis)
	- Whitemouth Croaker (Curvina - Micropogonias furnieri)
	- Mullet (Tainha - Mugil liza)
- Uncommon:
	- Bluefish (Anchova - Pomatomus saltatrix)
	- Stingray (Arraia - Hypanus americanus)
	- Snook (Robalo - Centropomus undecimalis)
- Rare:
	- Flounder (Linguado - Paralichthys orbignyanus)
	- Brazilian Sharpnose Shark (Cação - Rhizoprionodon lalandii)
	- Dusky Grouper (Garoupa - Epinephelus marginatus)
- Epic:
	- Giant Grouper (Mero - Epinephelus itajara)

Special catches:

- Trash (Lixo - no scientific name, 0 gold)
- Treasure Chest (Baú do Tesouro - no scientific name, only one per match, 20 gold)

Hybrid stock limits (V1, tuned for 6 players and 5 rounds):

- Common fish: unlimited (probability-based only).
- Uncommon fish: unlimited (probability-based only).
- Rare fish: 18 total per match (6 per rare species).
- Epic fish: 6 total per match.
- Treasure Chest: 1 total per match.
- Trash: unlimited.

Fishing resolution (V1):

- Every player gets 1 mandatory catch per turn.
- A +fish card adds +1 catch, up to a maximum of 2 catches per turn in V1.
- If the player is in Outer C or Outer D, roll for Treasure Chest first if it has not appeared yet.
- Then roll the rarity band based on the sea:
	- Lagoon: 65% common, 10% uncommon, 25% trash.
	- Outer A: 55% common, 35% uncommon, 10% trash.
	- Outer B: 40% common, 40% uncommon, 20% rare.
	- Outer C: 20% common, 35% uncommon, 40% rare, 5% trash.
	- Outer D: 10% common, 20% uncommon, 45% rare, 25% epic.
- Within each rarity band, choose the specific fish by weighted order or equal split.
- Treasure Chest, if found, replaces the normal fish catch for that roll.
- If a rolled rarity pool is depleted, fallback to the next lower rarity:
	- epic -> rare
	- rare -> uncommon
	- uncommon -> common

Selling:

- Fish can only be sold in the lagoon.
- Sold fish generate immediate coins.
- Holding fish for set completion can give higher value later.

Suggested base fish values (V1):

- Common: 2 gold
- Uncommon: 4 gold
- Rare: 7 gold
- Epic: 12 gold

Repair and sinking economy (V1):

- If a player sinks, they lose 100% of fish cargo.
- If a player sinks, they lose 30% of current gold (rounded down).
- Repairing in the lagoon costs 2 gold per HP restored.
- Suggested repair cap: 4 HP restored per round.

## 9) Fish sets (set collection)

Suggested sets:

- Local School: 3 different common fish -> +4 gold bonus.
- Export Batch: 2 uncommon + 1 rare -> +8 gold bonus.
- Ocean Trophy: 2 rare + 1 epic -> +15 gold bonus.

Set rules:

- Set can be sold at any time in Market Phase.
- Selling a set consumes all fish used by that set.

Negotiation rules (V1):

- Negotiation is optional and occurs in Phase 1.
- Players may negotiate regardless of sea position.
- Allowed trades: fish-for-fish, fish-for-gold, and gold-for-gold.
- Suggested limit: one completed negotiation per player per round.
- Trades are immediate and must be accepted by both players.
- No deferred promises (future turn deals are not enforceable by rules).

## 10) Action cards

Initial deck with Florianopolis-themed cards (events on hold):

- Witches of the Lagoon: gain +1 in the next battle you fight this round.
- South Wind: if you defend a sea, the attacker gets -1 in the first combat exchange.
- Conceicao Mist: cancel one attack targeting you this turn.
- Channel Passage: move to any sea this turn and immediately challenge the occupant if the sea is already taken.
- Naufragados Wreck: if you win a battle in Outer D, gain +2 gold (resolve in Reward/Consequence phase).
- Tainha Season: +1 fish in mandatory fishing this turn.
- Fisherman's Blessing: heal 2 HP.
- Net of the Rendeiras: convert 1 common fish into 1 uncommon fish.
- Wharf Bargain: +20% sale value in this Market Phase.
- Hidden Current: if you win a battle, the loser gives you 1 fish (resolve in Reward/Consequence phase).
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

## 11) Sea hazards

Environmental damage is resolved in Phase 4 (Mandatory Fishing), after movement/battle decisions are complete.

Roll 1d6 for the sea where the player ends the turn.

Hazard table (V1):

- Lagoon (Lagoa):
	- Any result: 0 damage.
	- Strategic role: safe hub for market and repairs.
- Outer A:
	- 1-2: 0 damage
	- 3-6: 1 damage
	- Expected damage: ~0.67 per turn
- Outer B:
	- 1: 0 damage
	- 2-5: 1 damage
	- 6: 2 damage
	- Expected damage: 1.00 per turn
- Outer C:
	- 1: 0 damage
	- 2 - 3: 1 damage
	- 4 - 6: 2 damage
	- Expected damage: ~1.33 per turn
- Outer D:
	- 1: 0 damage
	- 2 - 4: 2 damage
	- 5 - 6: 3 damage
	- Expected damage: 2.00 per turn

Persistence pressure (anti-camping):

- If a player stays in the same outer sea for a consecutive turn, add +1 environmental damage (cap +1).
- This modifier resets when the player changes sea or returns to the lagoon.

Hazard flavor sources may include:

- Storm.
- Hidden rocks.
- Strong current.
- Sea monster.

## 12) Synchronization rules for the online version

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

## 13) Match flow (high-level)

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

## 13.1) Quick mode for evaluation

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

## 13.2) How to support both modes without duplicating work

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

## 14) Useful metrics and statistics

For match history and player profile:

- Total coins per match.
- Fish caught by rarity.
- Completed sets.
- Damage dealt/taken.
- Number of times sunk.
- Win rate.
- Most visited sea.

## 15) MVP prototype focus

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

## 16) Open decisions to align as a team

- Exact number of rounds.
- Final damage values by sea.
- Rarity curve by zone.
- Initial card count per player.
- Final sinking rule (respawn vs elimination).
- Desired randomness level (more strategy vs more chaos).

## 17) Temporary game name

Suggested internal codename:

- Five Seas: Fisher Clash

Can be changed later with no technical impact.
