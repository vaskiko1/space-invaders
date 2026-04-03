# 🎮 Game Dev Learning Plan — Space Defender
**For:** 14-year-old beginner programmer  
**Duration:** 20 weeks (~3 sessions/week, 45–60 min each)  
**Goal:** Build and publish a complete Space Defender game using Python + Pygame

---

## Overview

| Phase | Title | Weeks | Focus |
|-------|-------|-------|-------|
| 1 | Python Basics | 1–4 | Variables, conditions, loops, functions |
| 2 | Pygame & Graphics | 5–8 | Game window, sprites, input, movement |
| 3 | Core Mechanics | 9–13 | Shooting, enemies, collisions, scoring |
| 4 | Polish & Content | 14–17 | Sound, animations, power-ups, high scores |
| 5 | Launch & Next Steps | 18–20 | Playtesting, publishing, portfolio |

---

## Tech Stack

| Tool | Purpose | Cost |
|------|---------|------|
| Python 3 | Programming language | Free |
| Pygame | Game library | Free |
| VS Code | Code editor | Free |
| Piskel / Aseprite | Pixel art sprites | Free / Paid |
| Bfxr / OpenGameArt | Sound effects & music | Free |
| GitHub | Code versioning & sharing | Free |
| itch.io | Game publishing platform | Free |

---

## Phase 1 — Python Basics
**Weeks 1–4 · ~12 sessions**

> Goal: Write real Python programs from scratch. By the end, build a complete text-based quiz game without any help.

### Week 1 — Setup + First Program

**Topics:**
- Install Python 3 and VS Code — understand what an IDE is
- Run the first script: print messages to the screen
- Variables — store a player name, a score, a lives count
- Data types: integers, floats, strings and booleans
- Basic arithmetic: `+`, `-`, `*`, `/`, `//` (integer division), `%` (remainder)
- f-strings for readable output: `f"Welcome, {player_name}!"`

**First code to write:**
```python
# My first game variables
player_name = "Astronaut"
score = 0
lives = 3
print(f"Welcome, {player_name}!")
print(f"Score: {score} | Lives: {lives}")
```

**Session goal:** See his own name printed on screen by the end of session 1.

---

### Week 2 — Input, Conditions & Decisions

**Topics:**
- Getting input from the user with `input()`
- `if` / `elif` / `else` — making decisions in code
- Comparison operators: `==`, `!=`, `>`, `<`, `>=`, `<=`
- Logical operators: `and`, `or`, `not`
- Type conversion: `int()`, `str()`, `float()`

**Mini exercise — number guessing game:**
```python
secret = 42
guess = int(input("Guess a number: "))
if guess == secret:
    print("You win!")
elif guess < secret:
    print("Too low!")
else:
    print("Too high!")
```

**Milestone:** A number guessing game that responds correctly to the player's input.

---

### Week 3 — Loops: Repetition Without Boredom

**Topics:**
- `while` loops — repeat until a condition is false
- `for` loops — repeat a fixed number of times
- `range()` — generating sequences of numbers
- `break` and `continue` — controlling loop flow
- Lists — storing multiple values (enemy list, bullet list preview)
- `append()`, `len()`, and indexing a list

**Game connection — spawning a wave:**
```python
enemies = []
for i in range(5):
    enemies.append(f"Enemy_{i}")

for e in enemies:
    print(f"{e} spawned!")
```

**Milestone:** The guessing game now gives 5 attempts in a loop and tells the player how many are left.

---

### Week 4 — Functions + Mini-Project

**Topics:**
- Defining functions with `def`
- Parameters and return values
- Why functions exist: reusable, readable code
- Variable scope — what exists inside vs outside a function
- Combining everything: variables + conditions + loops + functions

**Mini-project — Space Quiz Game:**
```python
def ask_question(question, correct_answer):
    reply = input(question + " ").strip().lower()
    if reply == correct_answer:
        print("Correct! +10 points")
        return 10
    else:
        print(f"Wrong! The answer was: {correct_answer}")
        return 0

score = 0
score += ask_question("What planet has rings?", "saturn")
score += ask_question("How many moons does Earth have?", "1")
score += ask_question("What is the closest star to Earth?", "sun")
print(f"\nFinal score: {score}/30")
```

**Milestone:** Complete space quiz game — multiple questions, score tracking, win/lose message.

---

### Phase 1 Learning Resources

#### 🇵🇹 Portuguese (primary)

| Resource | Type | Cost | Use |
|----------|------|------|-----|
| **Curso em Vídeo — Python 3 (Gustavo Guanabara)** | Video series | Free | Weeks 1–3 as main reference |
| **Hora de Codar — Python para Iniciantes (Matheus Battisti)** | YouTube | Free | Weeks 2–4 as complement |

- Guanabara: https://www.cursoemvideo.com/curso/python-3-mundo-1/
- Battisti: https://www.youtube.com/@matheusbattisti

#### 🇬🇧 English (supplement)

| Resource | Type | Cost | Use |
|----------|------|------|-----|
| **freeCodeCamp — Python for Beginners (4h course)** | YouTube | Free | Weeks 2–4 to reinforce concepts |
| **CS50P — Introduction to Programming with Python (Harvard)** | Video + exercises | Free | Week 3–4 as stretch challenge |
| **Codecademy — Learn Python 3** | Interactive browser | Free tier | Week 1 warm-up before local setup |
| **Invent Your Own Games with Python — Al Sweigart** | Free PDF book | Free | Weeks 2–4 as bedtime reading |

- freeCodeCamp: https://www.youtube.com/watch?v=rfscVS0vtbw
- CS50P: https://cs50.harvard.edu/python/
- Codecademy: https://www.codecademy.com/learn/learn-python-3
- Free book: https://inventwithpython.com/invent4thed/

#### Tips for Phase 1
- **Start in Portuguese, switch to English when stuck.** Hearing the same concept twice in different languages cements it.
- **No copy-paste.** Every snippet must be typed by hand.
- **Celebrate error messages.** Red errors are clues, not failures.
- **The week 4 project is the most important.** A broken self-written quiz beats a perfect copy-pasted one.

---

## Phase 2 — Pygame & Graphics
**Weeks 5–8 · ~12 sessions**

> Goal: Get something moving on screen. By the end, control a spaceship with arrow keys.

### Week 5 — Opening a Window

**Topics:**
- Installing Pygame: `pip install pygame`
- Creating a game window with a title and background colour
- Understanding pixel coordinates: (0,0) is top-left
- Drawing shapes: `pygame.draw.rect()`, `pygame.draw.circle()`
- RGB colour tuples: `(255, 0, 0)` is red
- Closing the window properly with the quit event

**First Pygame program:**
```python
import pygame
pygame.init()
screen = pygame.display.set_mode((800, 600))
pygame.display.set_caption("Space Defender")
clock = pygame.time.Clock()

running = True
while running:
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            running = False

    screen.fill((10, 10, 30))  # dark space background
    pygame.draw.rect(screen, (0, 200, 255), (370, 500, 60, 30))  # ship placeholder
    pygame.display.flip()
    clock.tick(60)

pygame.quit()
```

**Milestone:** A game window stays open and shows a coloured rectangle.

---

### Week 6 — The Game Loop & Keyboard Input

**Topics:**
- The game loop in depth: event → update → draw
- `pygame.event.get()` — handling events
- `pygame.key.get_pressed()` — smooth keyboard movement
- Moving an object with arrow keys
- Keeping objects inside screen boundaries with `max()` / `min()`
- `pygame.time.Clock` and frame rate (FPS)

**Moving ship with boundaries:**
```python
keys = pygame.key.get_pressed()
if keys[pygame.K_LEFT]:
    ship_x -= 5
if keys[pygame.K_RIGHT]:
    ship_x += 5
ship_x = max(0, min(800 - ship_width, ship_x))
```

**Milestone:** The rectangle moves left and right and stops at the screen edges.

---

### Week 7 — Sprites & Images

**Topics:**
- Loading images: `pygame.image.load()`
- `pygame.transform.scale()` — resize sprites
- Transparency with `.convert_alpha()`
- Drawing images with `screen.blit()`
- Introduction to Piskel — design a pixel-art spaceship
- Organising assets in an `assets/` folder

**Sprite design session:** Design the player's spaceship in Piskel (https://www.piskelapp.com). Export as PNG, load into the game.

**Milestone:** A pixel-art spaceship the student designed himself moves across the screen.

---

### Week 8 — Starfield Background & Mouse

**Topics:**
- Creating a scrolling starfield (list of star positions, move and wrap)
- Mouse position with `pygame.mouse.get_pos()`
- Mouse click events
- Displaying text on screen: `pygame.font.SysFont()`, `font.render()`
- Drawing the score counter and lives display

**Scrolling stars:**
```python
stars = [(random.randint(0, 800), random.randint(0, 600)) for _ in range(100)]

for i, (sx, sy) in enumerate(stars):
    sy += 1  # scroll down
    if sy > 600:
        sy = 0
        sx = random.randint(0, 800)
    stars[i] = (sx, sy)
    pygame.draw.circle(screen, (255, 255, 255), (sx, sy), 1)
```

**Milestone:** Game has a scrolling starfield, the player's sprite moves smoothly, and score/lives display on screen.

---

### Phase 2 Learning Resources

| Resource | Language | Notes |
|----------|---------|-------|
| **Pygame official docs** | English | https://www.pygame.org/docs/ |
| **Clear Code — Pygame beginner series (YouTube)** | English | Best video series for Pygame specifically |
| **Tech With Tim — Pygame tutorials (YouTube)** | English | More projects-focused, good for motivation |
| **KidsCanCode — Game Development with Pygame** | English | https://kidscancode.org/lessons/ — free, game-focused |

---

## Phase 3 — Core Mechanics
**Weeks 9–13 · ~15 sessions**

> Goal: A fully playable game. Shoot enemies, lose lives, see a game over screen.

### Week 9 — Shooting Bullets

**Topics:**
- Lists of objects — managing multiple bullets at once
- Creating a bullet on spacebar press
- Moving all bullets upward every frame
- Removing bullets that go off screen (list comprehension)
- Limiting fire rate with a timer

**Bullet system:**
```python
bullets = []

# Fire on spacebar
if keys[pygame.K_SPACE] and fire_timer <= 0:
    bullets.append([ship_x + ship_width // 2, ship_y])
    fire_timer = 15  # frames between shots

# Move and draw bullets
bullets = [[bx, by - 8] for bx, by in bullets if by > 0]
for bx, by in bullets:
    pygame.draw.rect(screen, (255, 255, 0), (bx, by, 4, 12))
```

---

### Week 10 — Enemies

**Topics:**
- Creating an enemy class (or a list of enemy dictionaries)
- Spawning enemies at the top with random x positions
- Moving enemies downward
- Increasing spawn rate over time for difficulty
- Removing enemies that leave the screen

**Enemy spawning:**
```python
import random

enemies = []
spawn_timer = 0

# Spawn new enemy every 60 frames
spawn_timer += 1
if spawn_timer >= 60:
    enemies.append({"x": random.randint(20, 760), "y": -40})
    spawn_timer = 0

# Move enemies
for e in enemies:
    e["y"] += 3

enemies = [e for e in enemies if e["y"] < 650]
```

---

### Week 11 — Collision Detection

**Topics:**
- `pygame.Rect` — the rectangle that wraps each object
- `rect.colliderect()` — did two rectangles overlap?
- Bullet vs enemy collision: destroy both, add score
- Enemy vs player collision: lose a life, remove enemy
- Understanding why collision detection is the heart of every game

**Collision check:**
```python
player_rect = pygame.Rect(ship_x, ship_y, ship_width, ship_height)

for enemy in enemies[:]:
    enemy_rect = pygame.Rect(enemy["x"], enemy["y"], 40, 40)
    if player_rect.colliderect(enemy_rect):
        lives -= 1
        enemies.remove(enemy)
    for bullet in bullets[:]:
        bullet_rect = pygame.Rect(bullet[0], bullet[1], 4, 12)
        if enemy_rect.colliderect(bullet_rect):
            score += 10
            enemies.remove(enemy)
            bullets.remove(bullet)
            break
```

---

### Week 12 — Score, Lives & HUD

**Topics:**
- Persistent score and lives variables
- Drawing a clean HUD (Heads-Up Display) at the top of the screen
- Creating an explosion effect (brief flash or sprite swap)
- Tracking the player's highest score in a variable

**HUD display:**
```python
font = pygame.font.SysFont("monospace", 24)
score_text = font.render(f"Score: {score}", True, (255, 255, 255))
lives_text = font.render(f"Lives: {lives}", True, (255, 100, 100))
screen.blit(score_text, (10, 10))
screen.blit(lives_text, (10, 40))
```

---

### Week 13 — Game Over & Restart

**Topics:**
- Game states: `"playing"`, `"game_over"`, `"start_screen"`
- Drawing different screens based on current state
- Restart: reset all variables and switch back to `"playing"`
- Start screen with title and "Press ENTER to play"
- Game over screen showing final score

**Game state machine:**
```python
state = "start"

if state == "start":
    # draw title screen, wait for ENTER
    if keys[pygame.K_RETURN]:
        state = "playing"

elif state == "playing":
    # all the game logic here
    if lives <= 0:
        state = "game_over"

elif state == "game_over":
    # draw game over screen
    if keys[pygame.K_r]:
        score, lives = 0, 3
        enemies.clear()
        bullets.clear()
        state = "playing"
```

**Milestone:** Fully playable prototype — can be lost, won, and restarted without relaunching the program.

---

### Phase 3 Learning Resources

| Resource | Language | Notes |
|----------|---------|-------|
| **Pygame collision docs** | English | https://www.pygame.org/docs/ref/rect.html |
| **Real Python — Pygame primer** | English | https://realpython.com/pygame-a-primer/ |
| **Al Sweigart — Making Games with Python & Pygame** | English | Free: https://inventwithpython.com/pygame/ |

---

## Phase 4 — Polish & Content
**Weeks 14–17 · ~12 sessions**

> Goal: Turn the prototype into a game worth sharing. Sound, variety, power-ups, saved high scores.

### Week 14 — Sound Effects

**Topics:**
- `pygame.mixer` — loading and playing sounds
- Sound vs music: short effects vs background loop
- Generate 8-bit sound effects with Bfxr (https://www.bfxr.net)
- Download free background music from OpenGameArt (https://opengameart.org)
- Playing sounds on shoot, explosion, power-up, and game over

```python
pygame.mixer.init()
shoot_sound = pygame.mixer.Sound("assets/shoot.wav")
explode_sound = pygame.mixer.Sound("assets/explode.wav")
pygame.mixer.music.load("assets/background.ogg")
pygame.mixer.music.play(-1)  # -1 = loop forever

# When firing:
shoot_sound.play()
```

---

### Week 15 — Multiple Enemy Types

**Topics:**
- Using a class (or type key in dictionary) to define different enemies
- Fast enemies (small, quick, low points)
- Armoured enemies (large, slow, need 2 hits, more points)
- Enemy sprites designed in Piskel
- Scaling difficulty: later waves have more armoured enemies

**Enemy types dictionary:**
```python
ENEMY_TYPES = {
    "scout":  {"speed": 5, "hp": 1, "points": 10, "color": (200, 50, 50)},
    "tank":   {"speed": 2, "hp": 3, "points": 30, "color": (50, 50, 200)},
}
```

---

### Week 16 — Power-Ups

**Topics:**
- Spawning power-up items when enemies are destroyed (random chance)
- Power-up types: shield, rapid fire, multi-shot
- Timed power-ups — effect lasts 10 seconds then expires
- Visual indicator showing active power-up and time remaining
- Introduction to: dictionaries for game state

**Power-up ideas:**
- 🛡️ **Shield** — absorbs one hit
- ⚡ **Rapid Fire** — halves the fire cooldown for 10s
- 💥 **Triple Shot** — fires 3 bullets in a spread

---

### Week 17 — High Scores (File I/O)

**Topics:**
- Reading and writing files with `open()`, `read()`, `write()`
- Saving the top score to `highscore.txt`
- Loading it on startup and comparing after each game
- Displaying "New High Score!" when beaten
- Introduction to try/except — what if the file doesn't exist yet?

```python
def load_high_score():
    try:
        with open("highscore.txt", "r") as f:
            return int(f.read())
    except FileNotFoundError:
        return 0

def save_high_score(score):
    with open("highscore.txt", "w") as f:
        f.write(str(score))
```

**Milestone:** Feature-complete game with sound, multiple enemies, power-ups, and a persistent high score.

---

### Phase 4 Learning Resources

| Resource | Language | Notes |
|----------|---------|-------|
| **Bfxr sound generator** | — | https://www.bfxr.net — free, browser-based |
| **OpenGameArt** | — | https://opengameart.org — free licensed assets |
| **Piskel sprite editor** | — | https://www.piskelapp.com — free browser-based |
| **Pygame mixer docs** | English | https://www.pygame.org/docs/ref/mixer.html |

---

## Phase 5 — Launch & Next Steps
**Weeks 18–20 · ~9 sessions**

> Goal: Ship it. A real game, published online, with source code on GitHub.

### Week 18 — Playtesting & Bug Fixing

**Topics:**
- Playtesting: give the game to friends and family, watch them play (don't explain anything)
- Writing down every bug and piece of feedback
- Prioritising fixes: what breaks the game vs what would be nice to fix
- Introduction to: reading your own code after time away from it
- Balancing: is the difficulty curve fair?

**Playtesting checklist:**
- [ ] Does the game start without errors on another computer?
- [ ] Can you always tell what's happening on screen?
- [ ] Does the difficulty feel fair at the start and challenging later?
- [ ] Is the game over screen clear?
- [ ] Does the high score save and reload correctly?

---

### Week 19 — Packaging & Publishing

**Topics:**
- Install PyInstaller: `pip install pyinstaller`
- Create a standalone `.exe`: `pyinstaller --onefile --windowed main.py`
- Test the packaged game on a clean machine (or ask someone without Python installed)
- Create a free account on itch.io (https://itch.io)
- Upload the game: write a description, add screenshots, set price to free
- Add a game cover image (design in Piskel or Canva)

```bash
# Package the game as a single executable
pyinstaller --onefile --windowed --name "SpaceDefender" main.py
# Output will be in: dist/SpaceDefender.exe
```

---

### Week 20 — GitHub & What's Next

**Topics:**
- Create a free GitHub account (https://github.com)
- Install Git: `git init`, `git add .`, `git commit -m "first commit"`
- Push to GitHub — first public repository
- Write a README.md for the project (what is the game, how to play, screenshots)
- Reflect: what was learned, what was hard, what to build next

**What's next — choose your path:**

| Path | Tool | Why |
|------|------|-----|
| More Python games | Pygame | Keep building on what's working |
| Professional 2D games | Godot + GDScript | Very similar to Python, free, industry-used |
| Minecraft-style 3D | Unity + C# | Bigger learning curve, but huge community |
| Web games | JavaScript + Phaser.js | Games playable directly in the browser |
| Mobile games | Godot (exports to Android/iOS) | Same tool, different target |

**Milestone:** 🚀 Published game on itch.io + source code on GitHub.

---

## Weekly Schedule Template

```
Monday    Session 1 — Watch tutorial video + take notes
Wednesday Session 2 — Write code from scratch (no copy-paste)
Friday    Session 3 — Mini-project or challenge exercise
Weekend   Optional — extra reading, game design sketching
```

---

## Parent Guide

### What to do
- **Play his game** at the end of each phase and react genuinely. This is the most powerful motivator.
- **Ask questions** instead of giving answers: "What do you think would happen if the bullet goes off screen?"
- **Celebrate bugs.** When something breaks, say: "Great — now we know exactly where the problem is."
- **Let him drive.** Resist typing for him, even when it's faster.

### What to avoid
- Solving problems for him — guiding with questions is always better
- Comparing progress to others
- Pushing to move faster than the schedule — consolidation matters more than speed

### Signs he's doing well
- He opens VS Code on his own without being asked
- He starts modifying the examples before finishing the exercise
- He talks about game ideas he wants to build next
- He explains a concept to you in his own words

---

## Completion Checklist

- [ ] Phase 1: Space quiz game runs and scores correctly
- [ ] Phase 2: Spaceship moves on screen with custom sprite
- [ ] Phase 3: Fully playable shoot-em-up with game over
- [ ] Phase 4: Sound, power-ups, multiple enemies, high score saved
- [ ] Phase 5: Game published on itch.io, code on GitHub

---

*Plan generated with Claude · Adjust pacing to your son's rhythm · Good luck!* 🚀
