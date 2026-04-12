# Transcendence - Online Board Game (Concept)

## 1) Overview

Online multiplayer game concept with fishing ships and light pirate-style conflict.

- Inspiration: a mix of Quartz + King of Tokyo.
- Players: 6 to 8 players per match.
- Objective: finish the game with the most money earned from selling fish.
- Core decision axis: risk vs reward between safer seas and more dangerous seas.

## 2) Map and seas

The board has 5 seas:

- 1 central lagoon (safe hub).
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

- If an outer sea is free, the player must resolve Battle Against the Tide before entering.
- If an outer sea is occupied, the incoming player must challenge the occupant in a battle.
- The loser of the battle always returns to the lagoon.
- The winner stays in the target sea.

Battle Against the Tide (empty outer sea only):

- The player rolls 1d6 with no combat modifiers.
- Success thresholds by sea:
	- Outer A: 2+
	- Outer B: 3+
	- Outer C: 4+
	- Outer D: 5+
- On success, the player enters and occupies the target sea.
- On failure, the player returns to the lagoon and takes no damage.
- This is not player-vs-player combat and does not trigger battle win/loss card effects.

The lagoon remains the central safe zone, the default return point after defeat, and the only shared market zone.

## 4) Win condition

- Match lasts 5 rounds (target match length: 30-40 minutes).
- At the end, the player with the most coins wins.
- Tiebreakers:
1. Treasure Chest obtained.
2. Highest number of epic fish caught during the match.
3. Highest number of rounds spent in Outer D.
4. Highest number of rare fish caught during the match.
5. Highest number of rounds spent in Outer C.

## 4.1) Initial setup

- Starting HP: 10.
- Starting gold: 0.
- All players start in the lagoon.
- Starting cargo limit: 4 fish slots.
- Players can only gain gold by selling fish or by card effects.

## 5) Turn structure

Each round has the following 6 phases:

1. Optional Trading and Market
- Players may negotiate with any player regardless of location.
- Fish can be sold only if the player is currently in the lagoon.

2. Action Cards
- Player may play action cards according to hand and turn limits.

3. Movement and Battles
- Player may move once to any sea.
- If the target sea is free outer sea, resolve Battle Against the Tide.
- If the target sea is occupied, an occupation battle starts.
- The loser returns to the lagoon.
- If the player moves to an occupied sea, battle is mandatory.
- If Battle Against the Tide succeeds on a free outer sea, they may fortify defenses.
- If the player moves to the lagoon, they may repair by paying gold or do nothing.

4. Mandatory Fishing
- Every player must fish at the end of the turn.
- Quantity and quality depend on sea and active effects.

5. Reward/Consequence Cards
- Resolve cards that trigger after fishing or after battle outcomes.
- Example cards in this phase: Naufragados Wreck, Hidden Current.

6. Optional Emergency Sale
- After hazards and reward/consequence effects, the player may sell fish even outside the lagoon.
- Emergency sale pays 50% of base fish value (round down).
- Set bonuses and market bonuses do not apply.
- Selling sets remains lagoon-only.

## 6) Combat system

Combat occurs when:

- a player tries to enter an occupied sea,
- a card creates direct conflict.

Suggested format for fast online combat:

- All ships have base attack 0 in V1, unless modified by cards.
- Each side rolls 1d6 + ship attack + card modifiers.
- Combat is resolved in a single exchange.
- The loser always takes 2 damage.
- If there is a tie, the defender wins.

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
- If the player has gold, they lose 30% of current gold, rounded down.
- If the player has no gold, they lose no gold.
- Player returns to the lagoon with 5 HP if they had gold, or 4 HP if they had no gold.

Repair note:

- The lagoon includes a repair dock.
- Players can pay gold to restore HP there.
- Repair should only be possible in the lagoon.

Design note:

- Avoiding permanent elimination improves online experience (nobody sits out too long).
- V1 has no permanent elimination mode.

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

Cargo limit:

- Each player has 4 fish slots in cargo.
- If cargo is full, the player must sell, swap, discard, or use an effect that frees space before gaining another fish.

Hybrid stock limits (V1, tuned for 6 players and 5 rounds):

- Common fish: unlimited (probability-based only).
- Uncommon fish: unlimited (probability-based only).
- Rare fish: 18 total per match (6 per rare species).
- Epic fish: 6 total per match.
- Treasure Chest: 1 total per match.
- Trash: unlimited.

Fishing resolution (V1):

- Every player gets exactly 1 mandatory catch per turn.
- Extra catches are never part of the base rule; they only happen through card effects.
- If a card grants a second catch, the player resolves two catches and keeps only one result.
- If the player is in Outer C or Outer D, roll for Treasure Chest first if it has not appeared yet.
- Then roll the rarity band based on the sea:
	- Lagoon: 70% common, 20% uncommon, 10% trash.
	- Outer A: 55% common, 30% uncommon, 10% rare, 5% trash.
	- Outer B: 32% common, 45% uncommon, 20% rare, 3% trash.
	- Outer C: 15% common, 35% uncommon, 49% rare, 1% trash.
	- Outer D: 5% common, 20% uncommon, 50% rare, 25% epic.
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

Optional emergency sale (end of round):

- A player outside the lagoon may sell individual fish for 50% of base value (round down).
- Set bonuses and market bonuses are lagoon-only and never apply in emergency sale.
- This rule exists as risk mitigation and does not change sea occupancy.

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
- Tide Choice: during mandatory fishing, you may make a second catch, then choose one of the two catches to keep and discard the other.
- Fisher's Swap: choose one fish from your cargo and one fish from another player; both fishes are exchanged.

Card system (V1 closed):

- Deck size: 24 cards.
- Starting hand: 2 cards per player.
- Draw timing: draw 1 card at the start of rounds 2 and 4.
- Hand limit: 3 cards (discard immediately if exceeded).

Card timing and limits:

- Action window: Phase 2 (Action Cards).
- Reaction window: combat and hazard checks only, when a card explicitly says so.
- Per-round limit: 1 action card + 1 reaction card.
- Phase 6 (Emergency Sale): no card can be played.

Targeting and conflict rules:

- Combat cards may only affect players in the same battle.
- Theft/swap cards may target any player with valid cargo.
- If a target has no valid fish, the card cannot be played on that target.
- Anti-focus rule: the same attacker cannot apply more than one hostile card to the same target in one round.

Economy card constraints:

- Wharf Bargain applies only to lagoon market sale.
- Wharf Bargain never applies to emergency sale.
- Tide Choice uses the same sea fishing table for both catches.
- If cargo is full during Tide Choice resolution, choose one final catch to keep and discard the other result.

Design constraints for cards:

- Keep card text short and deterministic for multiplayer sync.
- Prioritize map positioning, fishing, and economy over pure damage.
- Card effects must stay consistent with the fixed V1 turn flow.

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
- Configuration choice (optional seed).

2. Setup
- Initial ship distribution.
- Initial placement in lagoon.
- Starting hand: 2 cards per player.

3. Rounds
- Execute turn phases for all players.
- Update partial ranking by coins.

4. Endgame
- Final fish sale.
- Set bonuses.
- Tiebreakers.
- Final screen with ranking and statistics.

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

- No open decisions for V1 at this time.
- Additional mode variants (including Quick Mode) are postponed to a future revision cycle.

## 17) Temporary game name

Suggested internal codename:

- Five Seas: Fisher Clash

Can be changed later with no technical impact.
