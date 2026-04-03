---
name: Phase 1 — Game setup
applyTo: "**/*.py"
description: "Set up project, Python env, and initial Pygame window with ship placeholder."
---

## Phase 1 — Game setup (implementation milestone)

### Goal
Initialize the game repository and make the first running Pygame preview.

### Tasks
1. Create `requirements.txt` with `pygame`.
2. Create `src/main.py` and implement:
   - `pygame.init()`
   - `screen = pygame.display.set_mode((800, 600))`
   - event loop with `QUIT` handling
   - `screen.fill((10, 10, 30))` + `pygame.display.flip()`
3. Add a ship placeholder as a rectangle at bottom center.
4. Add frame rate control with `pygame.time.Clock()` and `clock.tick(60)`.
5. Confirm game starts and closes cleanly.

### Validation
- `python -m src.main` displays a window with dark background and ship rectangle.
- no errors on close.
