# Space Invaders - ASCII Game

Classic arcade game Space Invaders with ASCII graphics written in C.

## Features

- 🎮 5 levels with increasing difficulty
- 👾 Three types of enemies (normal, fast, strong)
- ⏱️ Timer system for each level
- 💯 Score tracking system
- ❤️ Lives system
- 🎯 Player and enemy shooting
- 🎨 ASCII graphics with beautiful interface
- ⏸️ Pause system

## Controls

- `A` - Move left
- `D` - Move right
- `SPACE` - Shoot
- `ESC` - Pause
- `Q` - Exit to menu

## Compilation and Running

### Using Makefile:

```bash
make          # Compile
make run      # Compile and run
make clean    # Clean
```

### Manually:

```bash
gcc -Wall -Wextra -O2 space_invaders.c -o space_invaders
./space_invaders
```

## Requirements

- GCC compiler
- Linux/Unix system (uses termios.h for terminal control)
- Terminal with UTF-8 support for correct character display

## Game Elements

### Enemies:
- `W` - Normal alien (10 points)
- `M` - Fast alien (20 points)
- `X` - Strong alien (30 points)

### Player:
- `<A>` - Your spaceship

### Projectiles:
- `|` - Player shots
- `*` - Enemy shots

## Game Rules

1. Destroy all enemies on the level
2. Avoid enemy bullets
3. Don't let enemies reach the bottom of the screen
4. Complete the level before time runs out
5. Progress to the next level with increased difficulty

## License

Free to use for educational purposes.
