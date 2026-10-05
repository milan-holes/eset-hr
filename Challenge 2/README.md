# Challenge 2: Bomberman-Style Arena

## Goal

Build a small grid-based arena inspired by Bomberman. Generate a map of a defined size, move a player around walls, and implement at least one automated enemy that pursues the player.

Use React or Vue with JavaScript or TypeScript. DOM/CSS grid or Canvas rendering is acceptable. No backend or game engine is required. Implement map generation, movement, and pathfinding yourself.

## Core Requirements

### 1. Generate and Render the Map

- Accept configurable `width` and `height`, including boundary tiles. Default to **13 columns by 11 rows**.
- Use zero-based coordinates: `x` is the column and `y` is the row.
- Make every boundary tile a wall.

```text
#######
#P....#
#.#.#.#
#.....#
#.#.#.#
#....E#
#######
```

Here `#` means wall, `.` means floor, `P` means player, and `E` means enemy.

### 2. Implement Player Movement

- Arrow keys move the player exactly one tile per keypress, horizontally or vertically.
- Prevent movement into walls or outside the map. Diagonal movement is not allowed.
- Moving onto the enemy's tile ends the game immediately.

Smooth movement, touch controls, and directional animations are not required.

### 3. Implement an Automated Enemy

- Every **500 ms**, the enemy moves one tile along a shortest walkable path toward the player's current position.
- Recalculate the path on each enemy tick, using the latest player position.
- Any shortest path is acceptable when several exist. The enemy may not move diagonally, pass through walls, or leave the map.
- When the enemy reaches the player, show a game-over state and stop both player and enemy movement.
- Clean up keyboard listeners and timers when the game component unmounts.

## Optional Extensions

Only attempt these after the core behavior works. They are not required to pass.

- Place a bomb that explodes after a delay, affecting tiles in four directions and stopping at walls.
- Add a restart action that resets positions and game state without duplicating timers.
- Add destructible walls or multiple enemies, defining how their movement and collisions work.
- Add focused tests for map generation, collisions, and shortest-path behavior.
