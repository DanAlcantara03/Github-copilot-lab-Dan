---
description: Game logic and rules for the SocOps bingo game implementation.
---

## Development Checklist
- [ ] Lint code for style issues
- [ ] Build project successfully
- [ ] Run tests and verify functionality

# Bingo Game Logic

## Game Rules
SocOps is a social bingo game where players get a 5x5 board with questions, find people who answer "YES", mark matches, and win with 5 in a row.

## Core Components

### BingoSquareData
- `Id`: Unique identifier (0-24)
- `Text`: Question text
- `IsMarked`: Marked state
- `IsFreeSpace`: Center free space

### BingoLine
- `Type`: Horizontal/Vertical/Diagonal
- `Index`: Position (0-4)

### GameState Enum
- `Start`, `Playing`, `Won`

## Logic Implementation

### Board Generation
Randomly selects 24 questions + free space from `Questions.cs`.

### Square Toggling
Toggles `IsMarked` for non-free spaces, triggers win check.

### Win Detection
Checks rows, columns, diagonals; returns first winning line.

### Persistence
Saves/loads game state to localStorage with versioning.

## Key Functions (BingoLogicService)
- `GenerateBoard()`: Creates random board
- `ToggleSquare(board, id)`: Marks/unmarks square
- `CheckBingo(board)`: Returns winning line or null
- `GetWinningSquareIds(line)`: Gets winning square IDs

## UI Integration
`BingoGameService` manages state, events notify UI changes. Winning highlights squares and shows modal.</content>
<parameter name="filePath">/workspaces/Github-copilot-lab-Dan/.github/instructions/bingo-game-logic.instructions.md