# Online Model

## Approach

The game should be server-authoritative: the server validates actions and defines the official game state.

## Responsibilities

### Server

- validate movement;
- resolve hazards and fishing;
- apply damage;
- control cards and market actions;
- publish events to all clients.

### Client

- send player intent;
- render game state;
- react to incoming events.

## Suggested events

- lobby:update
- game:start
- turn:begin
- player:move
- hazard:result
- fishing:result
- market:sell
- card:played
- player:sunk
- game:end

## Additional idea

Since rounds are short, networking should prioritize quick response and simple reconnection. This prevents a dropped connection from ruining the match experience.