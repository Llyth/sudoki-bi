# sudoki-bi
sudoki-bi is a solver and generator for the game called "sudoku".

----------
## Delivery

Binary name: see below

Repository name: PPP_sudoki-bi

Repository rights: tony1.sam@epitech.eu; louis1.vandenbossche@epitech.eu

```markdown
- Your repository must contain the totality of your source files, but no useless files (binary, temp files, obj files, ...).
- All the bonus files (including a potential specific Makefile) should be in a directory named bonus.
- Error messages have to be written on the error output, and the program should then exit with the 84 error code (0 if there is no error).
```

----------
## Turn-in methods

You must have 2 folders : solver with a binary named "**solver**" in it, generator with binary named "**generator**" in it.

Each folder must contain a Makefile compiling their respective binary and a Makefile at the root that must compile all binaries.

```markdown
The Makefile at the root must not contain redundant recipes and therefore use as much as possible from existing Makefiles.
```

```console
~/PPP_sudoki-bi$ ls -R
.:
Makefile generator solver

./generator:
Makefile generator [...]

./solver:
Makefile solver [...]
```

----------
## Sudoku ? Késako ?

```markdown
Sudoku (/suːˈdoʊkuː, -ˈdɒk-, sə-/; Japanese: 数独, romanized: sūdoku, lit 'digit-single'; originally called Number Place) is a logic-based, combinatorial number-placement puzzle.
In classic Sudoku, the objective is to fill a 9 × 9 grid with digits so that each column, each row, and each of the nine 3 × 3 subgrids that compose the grid (also called "boxes", "blocks", or "regions") contain all of the digits from 1 to 9.
The puzzle setter provides a partially completed grid, which for a well-posed puzzle has a single solution.

Source : https://en.wikipedia.org/wiki/Sudoku
```

----------
## Specifications

**Usage**
The solver must be able to receive the grid to solve as standard input as follows and print the solved grid on the standard output:

```console
~/PPP_sudoki-bi$ ./solver << EOF
>|------------------|
>|       2 6   7   1|
>| 6 8     7     9  |
>| 1 9       4 5    |
>| 8 2   1       4  |
>|     4 6   2 9    |
>|   5       3   2 8|
>|     9 3       7 4|
>|   4     5     3 6|
>| 7   3   1 8      |
>|------------------|
>EOF
|------------------|
| 4 3 5 2 6 9 7 8 1|
| 6 8 2 5 7 1 4 9 3|
| 1 9 7 8 3 4 5 6 2|
| 8 2 6 1 9 5 3 4 7|
| 3 7 4 6 8 2 9 1 5|
| 9 5 1 7 4 3 6 2 8|
| 5 1 9 3 2 6 8 7 4|
| 2 4 8 9 5 7 1 3 6|
| 7 6 3 4 1 8 2 5 9|
|------------------|
```

If there is no solution you must print "**sudoki-bi: No solution found.**" on the same output.

The generator must generate a sudoku grid that your solver can solve and print the grid to solve on the standard output:

```console
~/PPP_sudoki-bi$ ./generator
|------------------|
|       2 6   7   1|
| 6 8     7     9  |
| 1 9       4 5    |
| 8 2   1       4  |
|     4 6   2 9    |
|   5       3   2 8|
|     9 3       7 4|
|   4     5     3 6|
| 7   3   1 8      |
|------------------|
```

```markdown
You are allowed to add other optional arguments; you must show them during the Review.
```

**Grid format**

```console
~/PPP_sudoki-bi$ ./generator > grid; cat -e grid
|------------------|$
|       6     4    |$
| 7         3 6    |$
|         9 1   8  |$
|                  |$
|   5   1 8       3|$
|       3   6   4 5|$
|   4   2       6  |$
| 9   3            |$
|   2         1    |$
|------------------|$
~/PPP_sudoki-bi$ ./solver < grid | cat -e
|------------------|$
| 5 8 1 6 7 2 4 3 9|$
| 7 9 2 8 4 3 6 5 1|$
| 3 6 4 5 9 1 7 8 2|$
| 4 3 8 9 5 7 2 1 6|$
| 2 5 6 1 8 4 9 7 3|$
| 1 7 9 3 2 6 8 4 5|$
| 8 4 5 2 1 9 3 6 7|$
| 9 1 3 7 6 8 5 2 4|$
| 6 2 7 4 3 5 1 9 8|$
|------------------|$
```

Your solver only accept this specific format. If there is something incorrect it must print "**sudoki-bi: Invalid format.**" on the error output.

```markdown
Tips: You should start with the solver.
```

----------
## Bonus

- Solving multiple grids at once
- Generating grids with only one solution
- Control grid difficulty
- Time solver and generator execution
- Play sudoku with Ncurses
