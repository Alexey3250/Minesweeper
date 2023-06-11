# Minesweeper AI

<img src="https://i.imgur.com/rDsUAv5.png">

This project is part of the [CS50's Introduction to Artificial Intelligence with Python](https://cs50.harvard.edu/ai/) course offered by Harvard University. It involves implementing an AI agent capable of playing the Minesweeper game. The AI uses the principles of propositional logic to make informed decisions about where to move next. It maintains a knowledge base of the current state of the game and uses this information to decide its next move.

## Implementation

The Minesweeper game logic is handled by the `Minesweeper` class. The game grid is a 2D array of cells. Cells are represented as tuples `(i, j)`, where `i` is the row index and `j` is the column index. Each cell is either safe (not containing a mine) or a mine.

The `MinesweeperAI` class is the AI agent that plays the game. It also has knowledge about the game grid, but only for cells it has revealed or inferred. The AI maintains a knowledge base of sentences, which are made up of cells (represented as sets of `(i, j)` tuples) and a count, which represents the number of mines in these cells.

## Methodology

The AI agent makes moves based on its current knowledge of the game grid. It follows these steps:

1. It first marks any known safe cells as moves it can make.
2. It then adds new sentences to its knowledge base based on the current state of the game.
3. The AI then uses inference to identify any new safe cells or mines. If a new safe cell is identified, it is added to the list of safe moves. If a new mine is identified, it is stored, and the information is used for future inferences.
4. The AI continues to make moves, adding knowledge and using inference until it can make no more safe moves.
5. If there are no safe moves left, the AI makes a random move.

## How to Run

To run the game:

1. Ensure you have Python 3.6 or later installed.
2. Install Pygame using pip:
   ```
   pip install pygame
   ```
3. Run the `runner.py` script:
   ```
   python runner.py
   ```

You can also adjust the game's difficulty by changing the `HEIGHT`, `WIDTH`, and `MINES` variables at the top of the `runner.py` file.

## Notes

This project makes heavy use of Python's object-oriented features and set operations. Understanding how sets work in Python is key to understanding how the AI maintains its knowledge base and uses inference to identify safe moves and mines.

Please note that this is a basic AI and it's not guaranteed to win all games. Minesweeper is NP-complete, and there will always be cases where the AI must guess to proceed. In these cases, the AI makes random moves.

## Course Info

This project is a part of [CS50's Introduction to Artificial Intelligence with Python](https://cs50.harvard.edu/ai/) course, a course offered by Harvard University that explores the concepts and algorithms at the foundation of modern artificial intelligence, diving into the ideas that give rise to technologies like game-playing engines, handwriting recognition, and machine translation.
