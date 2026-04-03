# Space Defender (Space Invaders clone)

A Python + Pygame project to build a complete space shooter game. This repository is structured as a development learning pipeline with phase-based milestones.

## Project goal
- Deliver a playable Space Defender game with moving player ship, shooting, enemies, scoring, lives, and levels.
- Add polish (sound, animation, power-ups, high score save) and launch packaging (PyInstaller, release asset archive).

## Contents
- full roadmap and phase details.
- `.github/copilot-instructions.md`: phase orchestration and Copilot workflow.
- `.github/instructions/phase1-game-setup.instructions.md`: initial Pygame setup.
- `.github/instructions/phase2-game-loop-and-input.instructions.md`: input and movement.
- `.github/instructions/phase3-core-mechanics.instructions.md`: bullets, enemies, collisions, score.
- `.github/instructions/phase4-polish-and-ui.instructions.md`: sound, UI, power-ups, high score.
- `.github/instructions/phase5-release-and-backlog.instructions.md`: release, packaging, backlog.

## Quick start
1. Set up Python 3 and virtual environment:
   - `python -m venv venv`
   - `venv\Scripts\activate` (Windows)
   - `pip install -r requirements.txt`
2. Run the initial game:
   - `python -m src.main`
3. Follow phase instructions under `.github/instructions/`.

## Phase summary
### Phase 1 — Python Basics / Game setup
- Get a window open
- Show ship placeholder
- Run a clean event loop

### Phase 2 — Pygame loop and input
- Add continuous game loop structure
- Move ship horizontally and clamp bounds
- Load ship sprite and background

### Phase 3 — Core mechanics
- Shoot bullets
- Spawn and move enemy waves
- Collide bullets/enemies and update score
- Manage lives and level progression

### Phase 4 — Polish and UI
- Sound effects and music
- Explosion / enemy animations
- Power-ups
- High score file storage

### Phase 5 — Release and backlog
- QA / tests
- README install/run/controls/credits
- Create PyInstaller build
- Package release artifact
- Add roadmap/backlog issues

## Where to contribute
- Add game features in `src/` and `assets/`.
- Keep a `CHANGELOG.md` optional for progress.
