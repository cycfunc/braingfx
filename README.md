# BrainGFX

BrainGFX is an improved version of [GBF](https://esolangs.org/wiki/Graphical_Brainfuck). BrainGFX consists of a grid of cells and a pointer to manipulate the cell. You can find some samples over [here](https://github.com/cycfunc/BrainGFX-Snippets/tree/master).

### Execution

Download and extract the zip file. Then navigate to the directory containing the `cc` file and type the following in the terminal

    $ javac cc/inversion/braingfx/BrainGFX.java
    $ java cc.inversion.braingfx.BrainGFX

### Commands

Cell's default maximum size is set to 256 and the image is 32x32.

- `+` increment the cell's value by 1. Value stored is modulo cell's maximum value.
- `-` decrement the cell's value by 1. Value stored is modulo cell's maximum value. Note that -1 = 255 mod 256.
- `.` prints the colour of the cell to the correspoding pixel (explained below).
- `<` perform action one (explained below).
- `>` perform action two (explaiend below).
- `[` if the current cell's value is 0, jump to the matching `]` bracket. Else ignore it.
- `] `if the current cell's value is not 0, jump to the matching `[` bracket. Else ignore it.
- `/` increments the mode by 1. Value stored is modulo 4.
- `\` decrements the mode by 1. Value stored is modulo 4.

#### Modes

There are four modes. In each mode, action one and action two makes pointer perform different things.

|            | Mode 0 | Mode 1 | Mode 2 | Mode 3 |
|------------|--------|--------|--------|--------|
| Action one | Left   | Up     | Right  | Down   |
| Action two | Right  | Down   | Left   | Up     |

Note that increasing the mode basically turns the operations clockwise (and vice versa for decreasing the mode). So mode 0 action 2 is right while mode 1 action 2 is down.

### Command Line Arguments

- `W` or `width`    : set image width
- `H` or `height`   : set image height
- `Z` or `zoom`     : set zoom
- `S` or `cellsize` : set cell's maximum value

|           | Default Value |
|-----------|---------------|
| Width     | 32            |
| Height    | 32            |
| Zoom      | 12            |
| Cell Size | 256           |

Example:

    $ java cc.inversion.braingfx.BrainGFX --W=12 --height=90 --Z=9

### Palette

3 bit, 8 color palette is used.

- ![0](https://raw.githubusercontent.com/inversioncc/BrainGFX/master/Colors/0.jpg) `0` : `#000000`
- ![1](https://raw.githubusercontent.com/inversioncc/BrainGFX/master/Colors/1.jpg) `1` : `#0000FF`
- ![2](https://raw.githubusercontent.com/inversioncc/BrainGFX/master/Colors/2.jpg) `2` : `#00FF00`
- ![3](https://raw.githubusercontent.com/inversioncc/BrainGFX/master/Colors/3.jpg) `3` : `#00FFFF`
- ![4](https://raw.githubusercontent.com/inversioncc/BrainGFX/master/Colors/4.jpg) `4` : `#FF0000`
- ![5](https://raw.githubusercontent.com/inversioncc/BrainGFX/master/Colors/5.jpg) `5` : `#FF00FF`
- ![6](https://raw.githubusercontent.com/inversioncc/BrainGFX/master/Colors/6.jpg) `6` : `#FFFF00`
- ![7](https://raw.githubusercontent.com/inversioncc/BrainGFX/master/Colors/7.jpg) `7 - 255` : `#FFFFFF`
