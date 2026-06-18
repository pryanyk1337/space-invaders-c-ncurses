# Cowboys of Space - ASCII Game

Classic arcade-style Space Invaders game with ASCII graphics written in C using ncurses.

## Features

- 🎮 5 levels with progressively increasing difficulty
- 👾 Three types of enemies:
  - **Normal aliens** (W) - 10 points, 1 hit
  - **Fast aliens** (M) - 20 points, 1 hit, moves faster
  - **Strong aliens** (X) - 30 points, 2 hits, armored
- ⏱️ Time limit system for each level (3 minutes)
- 💯 Score tracking with level multipliers
- ❤️ 3 lives system
- 🎯 Player and enemy shooting mechanics
- 🎨 Colorful ASCII graphics with Unicode art
- ⏸️ Pause functionality
- 📊 Dynamic difficulty scaling (more enemies, faster movement, increased fire rate)

## Controls

### In Menu:
- `↑`/`↓` or `W`/`S` - Navigate menu
- `Enter` or `1-3` - Select option
- `ESC` - Exit game

### In Game:
- `A` or `←` - Move ship left
- `D` or `→` - Move ship right
- `SPACE` - Fire weapon
- `ESC` - Pause game
- `Q` - Quit to main menu

## Requirements

- GCC compiler
- **ncursesw library** (wide character support for Unicode)
- Linux/Unix system or WSL on Windows
- Terminal with UTF-8 and color support

### Installing Dependencies:

**Debian/Ubuntu/WSL:**
```bash
sudo apt-get update
sudo apt-get install gcc make libncursesw5-dev
```

**Fedora/RHEL:**
```bash
sudo dnf install gcc make ncurses-devel
```

**Arch Linux:**
```bash
sudo pacman -S gcc make ncurses
```

**macOS:**
```bash
brew install gcc make ncurses
```

## Compilation and Running

### Using Makefile (Recommended):

```bash
make          # Compile the game
make run      # Compile and run
make clean    # Remove compiled files
make rebuild  # Clean and rebuild
```

### Manual Compilation:

```bash
gcc -Wall -Wextra -O2 -std=c11 main.c game_logic.c menu.c render.c -o space_invaders -lncursesw
./space_invaders
```

**Important:** Use `-lncursesw` (with 'w') for proper Unicode character support!

## Running on Different Systems

### Native Linux:
Works perfectly out of the box. Just compile and run.

### WSL (Windows Subsystem for Linux):
**Recommended:** Use VS Code integrated terminal for best experience:
1. Open project folder in VS Code
2. Open integrated terminal (`Ctrl + ~`)
3. Run: `make run`

**Alternative:** Windows Terminal with proper settings:
- Ensure UTF-8 locale is set: `export LANG=en_US.UTF-8`
- Use a Unicode-capable font (Cascadia Code/Mono recommended)
- May experience slight flickering (WSL limitation)

### Setting Up UTF-8 Support:

If you see broken characters, ensure UTF-8 locale:
```bash
# Check current locale
locale

# Set UTF-8 locale (if needed)
export LANG=en_US.UTF-8
export LC_ALL=en_US.UTF-8

# Add to ~/.bashrc to make permanent
echo 'export LANG=en_US.UTF-8' >> ~/.bashrc
echo 'export LC_ALL=en_US.UTF-8' >> ~/.bashrc
```

## Project Structure

```
space-invaders-c-ncurses-main/
├── game.h          # Header file with structures and function declarations
├── main.c          # Entry point and main game loop
├── game_logic.c    # Core game logic (movement, shooting, collisions)
├── menu.c          # Menu system and UI screens
├── render.c        # Rendering and ncurses initialization
├── Makefile        # Build configuration
└── README.md       # This file
```

## Game Elements

### Player:
- `<A>` - Your spaceship

### Enemies:
- `W` - Normal alien (10 points, 1 HP)
- `M` - Fast alien (20 points, 1 HP, increased speed)
- `X` - Strong alien (30 points, 2 HP, requires 2 hits)

### Projectiles:
- `|` - Player bullets
- `*` - Enemy bullets

## Gameplay

1. **Objective:** Destroy all enemies on each level before time runs out
2. **Avoid:** Enemy bullets and don't let enemies reach the bottom
3. **Progression:** Complete all 5 levels with increasing difficulty
4. **Difficulty scaling:**
   - More enemies spawn each level (up to 40 maximum)
   - Enemies move faster (speed increases per level)
   - Enemy fire rate increases
   - More enemy variety (fast and strong types appear in later levels)
5. **Lives:** You start with 3 lives - avoid enemy fire!
6. **Time limit:** Complete each level within 3 minutes

## Game Rules

1. Clear all enemies to advance to the next level
2. Avoid getting hit by enemy bullets (lose 1 life per hit)
3. Don't let enemies reach the bottom of the screen (instant game over)
4. Complete the level before the timer expires
5. Strong enemies (X type) require 2 hits to destroy
6. Score increases with each level's difficulty multiplier

## Tips

- Prioritize strong enemies (X) early - they take 2 hits
- Keep moving to avoid enemy fire
- Watch the timer - don't spend too long on single enemies
- Fast enemies (M) appear more frequently in higher levels
- Enemy fire rate increases significantly in later levels

## Troubleshooting

**Broken/Missing Characters:**
- Ensure you compiled with `-lncursesw` (not `-lncurses`)
- Check UTF-8 locale: `locale charmap` should show `UTF-8`
- Use a proper terminal (VS Code terminal, GNOME Terminal, Konsole, etc.)

**Screen Flickering:**
- Normal behavior in some terminals (especially WSL)
- Use VS Code integrated terminal for smoothest experience
- On native Linux, flickering should be minimal

**Compilation Errors:**
- Install `libncursesw5-dev` (Debian/Ubuntu) or `ncurses-devel` (Fedora/RHEL)
- Ensure `gcc` and `make` are installed

## Technical Details

- **Language:** C11
- **Library:** ncursesw (wide character ncurses)
- **Compiler Flags:** `-Wall -Wextra -O2 -std=c11`
- **Locale Support:** UTF-8 required for proper rendering

## License

Free to use for educational purposes.

---

**Enjoy defending Earth from the alien invasion, Space Cowboy! 🚀👾**
