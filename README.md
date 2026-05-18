# so_long

A small 2D top-down game built in C as part of the 42 school curriculum. The player navigates a grid-based map, collects all items, and reaches the exit.

## Features

**Mandatory**
- Grid-based movement (W/A/S/D or arrow keys)
- Animated player sprites (front, back, left, right)
- Move counter printed to the terminal
- Map validation with detailed error messages

**Bonus**
- Animated coins (10-frame sprite cycle)
- Animated door (4-frame sprite cycle)
- Enemy sprites with patrol movement
- Move counter rendered on screen
- Enemy collision ends the game

## Dependencies

- [MLX42](https://github.com/codam-coding-college/MLX42) — graphics library (included in `lib/MLX42`)
- [libft](lib/libft) — custom C utility library
- [GLFW](https://www.glfw.org/) — required by MLX42

Install GLFW on macOS:
```bash
brew install glfw
```

## Building

```bash
# Mandatory
make

# Bonus
make bonus

# Clean
make clean   # remove object files
make fclean  # remove object files + executables
make re      # full rebuild
```

## Usage

```bash
./so_long maps/map.ber
./so_long_bonus maps/map.ber
```

## Map Format

Maps use the `.ber` extension and are plain text grids. Valid characters:

| Char | Meaning |
|------|---------|
| `0`  | Empty ground |
| `1`  | Wall |
| `C`  | Collectible (coin) |
| `E`  | Exit (door) |
| `P`  | Player start position |

**Rules**
- The map must be rectangular and fully enclosed by walls (`1`)
- Exactly one player (`P`) and one exit (`E`)
- At least one collectible (`C`)
- A valid path must exist from `P` to `E` and all `C` tiles
- Bonus: no two enemies may occupy the same row

Example:
```
11111
1P0C1
100E1
11111
```

## Project Structure

```
so_long/
├── manda/          # mandatory sources
│   ├── include/
│   └── src/
├── bonus/          # bonus sources
│   ├── include/
│   └── src/
├── textures/       # PNG sprite assets
├── lib/
│   ├── libft/      # custom C library
│   └── MLX42/      # graphics library
└── Makefile
```

## Author

**aaitelka** — aaitelka@student.1337.ma
