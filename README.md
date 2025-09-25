# Classic Minesweeper Game with AI Assist

A Python implementation of the classic Minesweeper game, featuring an AI that can play the game intelligently. The game is built using `pygame` for the graphical interface.

## Features

- **Classic Minesweeper Gameplay**: Play the traditional Minesweeper game with customizable board sizes and mine counts.
- **AI Integration**: Watch the AI make safe moves and infer mine locations using solely logical knowledge reasoning.
- **User-Friendly Interface**: A clean and interactive UI built using `pygame`.

## How It Works

The AI uses **logic and math** to solve the board:

- **Clues as equations**  
  Each revealed number is turned into a constraint.  
  *Example: if a cell shows “2”, then exactly 2 of its 8 neighbors are mines.*

- **Knowledge as sentences**  
  A sentence looks like `{A, B, C} = 1`, meaning *exactly one of A, B, or C is a mine*.

- **Direct deductions**  
  - If `count = 0` → all cells in the set are **safe**.  
  - If `count = number of cells` → all cells in the set are **mines**.

- **Subset rule (logical subtraction)**  
  If `{A, B, C} = 1` and `{A, B, C, D} = 2`,  
  then subtract → `{D} = 1` → **D is a mine**.

- **Iterative reasoning**  
  The AI loops through its knowledge, marking new safes/mines and generating new equations until no further progress can be made.

- **Fallback move**  
  If no logical move exists, the AI picks a random unexplored cell that isn’t known to be a mine.

## Screenshots

### Welcome Screen
![Welcome Screen](screenshots/welcome-screen.png)

### Gameplay
![Gameplay](screenshots/game.png)

### AI Making Moves
![AI Moves](screenshots/ai-moves.png)

## How to Play

1. **Start the Game**: Run the `runner.py` file to launch the game, press "Play Game" button.
2. **Gameplay**:
   - Left-click to reveal a cell.
   - Right-click to flag a cell as a mine.
   - Use the "AI Move" button to let the sweeperAI make a move.
3. **Win Condition**: Flag all mines correctly to win the game.
4. **Lose Condition**: Reveal a mine to lose the game.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/minesweeper.git
   cd minesweeper
    ```
2. Install dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3. Run the game:
    ```bash
    python runner.py
    ```

## Project Structure
```
.
├── assets/                 # Game assets
│   ├── images/
│   │   ├── flag.png
│   │   └── mine.png
├── minesweeper.py          # Game logic and AI implementation
├── runner.py               # Main game loop and UI
├── requirements.txt        # Python dependencies
├── .gitignore              # Ignored files for Git
├── README.md               # Project documentation
└── screenshots/            # Game Screenshots
```

## Requirements
- Python 3.10+
- `pygame` library

## Controls
- Left-Click: Reveal a cell.
- Right-Click: Flag or unflag a cell.
- AI Move Button: Let the AI make a move.
- Reset Button: Restart the game.

---

<p align="center">
  Project by <a href="https://github.com/ashworth3">@ashworth3</a>
</p>
