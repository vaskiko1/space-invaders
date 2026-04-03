---
name: Phase 4 — Polish and UI
applyTo: "**/*.py"
description: "Add polish features: sound, effects, power-ups, menus, and high score persistence."
---

## Phase 4 — Polish and UI

### Goal
Make the game feel complete and polished for release.

### Tasks
1. Add audio: ship fire, enemy hit, player hit, background music using `pygame.mixer`.
2. Add animated movement for explosion effects and enemy sprites.
3. Implement power-ups: extra life, rapid fire, shield; spawn occasionally.
4. Add a start menu and pause menu with keyboard controls.
5. Persist high scores to `data/highscores.json` using JSON read/write.
6. Add instructions screen for controls.

### Validation
- sound plays correctly and can be muted/unmuted.
- power-ups apply to player and show feedback.
- high scores persist across runs.
