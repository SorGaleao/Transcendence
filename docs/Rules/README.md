# Transcendence - Rules Structure

This directory organizes the game draft into smaller files to make evolution, testing, and implementation easier.

## Structure

- [Overview](core/overview.md)
- [Map and seas](core/map-and-seas.md)
- [Turn flow and actions](core/turn-flow-and-actions.md)
- [Combat, health, and elimination](core/combat-health-and-elimination.md)
- [Fishing and economy](core/fishing-and-economy.md)
- [Quick mode](modes/quick-mode.md)
- [Normal mode](modes/normal-mode.md)
- [Online model](networking/online-model.md)
- [MVP](roadmap/mvp.md)
- [Open decisions](roadmap/open-decisions.md)

## Core idea

Both modes share the same game core. Quick mode reduces duration and complexity, while Normal mode expands interactions and strategic depth.

## Tunables to test later

- number of rounds per mode;
- base damage per sea;
- crowding bonus;
- starting hand size;
- fishing and selling limits;
- rarity curve per sea.
