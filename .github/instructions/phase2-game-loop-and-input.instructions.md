---
name: Phase 2 — Game loop and input
applyTo: "**/*.py"
description: "Implement continuous game loop, player ship movement, screen boundaries, and asset loading."
---

## Phase 2 — Game loop and input

### Goal
Enable responsive ship control in the game loop.

### Tasks
1. In `src/main.py`, move logic into functions `handle_events`, `update`, `draw`, `main`.
2. Use `pygame.key.get_pressed()` for left/right movement of the ship.
3. Keep ship inside horizontal bounds using `max`/`min`.
4. Replace rectangle with real sprite loaded from `assets/player.png` and scaled.
5. Add background starfield as list of star positions updated each frame.
6. Add debugging text HUD showing FPS and score placeholder.

### Validation
- ship moves smoothly with arrow keys or A/D.
- ship stops at edges and stays visible.
- game loop retains 60 FPS target.
