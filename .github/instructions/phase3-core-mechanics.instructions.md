---
name: Phase 3 — Core mechanics
applyTo: "**/*.py"
description: "Add shooting, enemy waves, collision detection, scoring, player lives, and level progression."
---

## Phase 3 — Core mechanics

### Goal
Implement game rules that make Space Defender playable.

### Tasks
1. Create classes `Player`, `Bullet`, `Enemy` in `src/game.py` or similar.
2. Fire bullets with `pygame.K_SPACE`; bullet list updates each frame.
3. Spawn enemies in waves at top of screen; each enemy has speed and path.
4. Detect collisions:
   - bullet vs enemy: remove both + add score
   - enemy vs player: decrement lives + reset enemy wave
5. Add `score`, `lives`, and `level` states in game controller.
6. Add simple UI overlay with these stats and `GAME OVER` state.

### Validation
- player can shoot, enemies are destroyed, score updates.
- lives decrement and game ends on zero.
- level increases after clearing current wave.
