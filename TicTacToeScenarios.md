# Tic Tac Toe – BDD Scenarios

This document defines behavior scenarios for the Tic Tac Toe game using the **Given–When–Then** format.  
The scenarios are based on the user stories defined for the project.

---

## 1. Game Start

### Scenario 1.1: Start a new game as player X
**Given** the user is on the game start screen  
**When** the user selects to play as "X" and presses the "Start Game" button  
**Then** an empty 3x3 board should be displayed  
**And** it should be visually indicated that it is player "X"'s turn.

### Scenario 1.2: Start a new game as player O
**Given** the user is on the game start screen  
**When** the user selects to play as "O" and presses the "Start Game" button  
**Then** an empty 3x3 board should be displayed  
**And** it should be visually indicated that it is player "O"'s turn.

---

## 2. Making a Move

### Scenario 2.1: Mark an empty cell
**Given** the game is in progress  
**And** it is the current player’s turn  
**And** there is at least one empty cell on the board  
**When** the player clicks on an empty cell  
**Then** the cell should display the current player’s mark ("X" or "O")  
**And** the cell should no longer be clickable.

### Scenario 2.2: Attempt to mark an occupied cell
**Given** a cell already contains a mark ("X" or "O")  
**When** the player attempts to click on that cell again  
**Then** the game should not change the existing mark  
**And** the current turn and game state should not be affected.

### Scenario 2.3: Switch turns after a valid move
**Given** it is player "X"'s turn  
**And** the board has at least one empty cell  
**When** player "X" marks a valid cell  
**Then** the game should switch the turn to player "O"  
**And** the visual turn indicator should be updated.

---

## 3. Win and Draw Determination

### Scenario 3.1: Win by row
**Given** player "X" already has two cells marked in the same row  
**And** there is a third empty cell in that row  
**When** player "X" marks the third cell in that row  
**Then** the game should detect that player "X" has won  
**And** a message indicating that "X" is the winner should be displayed  
**And** further moves should be prevented.

### Scenario 3.2: Win by column
**Given** player "O" already has two cells marked in the same column  
**And** there is a third empty cell in that column  
**When** player "O" marks the third cell in that column  
**Then** the game should detect that player "O" has won  
**And** a message indicating that "O" is the winner should be displayed  
**And** further moves should be prevented.

### Scenario 3.3: Win by diagonal
**Given** player "X" already has two cells marked in a diagonal  
**And** there is a third empty cell in that diagonal  
**When** player "X" marks the third cell in that diagonal  
**Then** the game should detect that player "X" has won  
**And** a message indicating that "X" is the winner should be displayed  
**And** further moves should be prevented.

### Scenario 3.4: Draw with no winner
**Given** all cells on the board are filled  
**And** there is no row, column, or diagonal with three matching marks  
**When** the player attempts to make a new move  
**Then** the game should indicate that the match has ended in a draw  
**And** no additional moves should be allowed.

---

## 4. Restarting the Game

### Scenario 4.1: Restart the game from the board
**Given** a game has ended in a win or a draw  
**When** the user presses the "Restart" button  
**Then** the board should be reset to an empty 3x3 state  
**And** no previous marks should remain on any cell  
**And** the game should allow the user to select who plays as "X" and "O", or keep the previously defined configuration.

### Scenario 4.2: Restart during an ongoing game
**Given** a game is in progress  
**When** the user presses the "Restart" button  
**Then** the board should be completely cleared  
**And** the game state should return to its initial state  
**And** the turn should be reset according to the selected configuration.

---

## 5. Intuitive User Interface

### Scenario 5.1: Clear board visualization
**Given** the user has started the game  
**When** the board is displayed  
**Then** the 9 cells should be clearly defined  
**And** they should be easily identifiable as clickable or selectable.

### Scenario 5.2: Visible turn indicator
**Given** the game is in progress  
**When** the turn changes from one player to another  
**Then** a visible indicator should be updated to show whose turn it is  
**And** the player should be able to easily identify when it is their turn.

### Scenario 5.3: Clear game status messages
**Given** the game has ended in a win or a draw  
**When** the result is displayed  
**Then** the message should clearly indicate whether there is a winner or a draw  
**And** the message should be visible enough to avoid confusion.

---

## 6. Local Multiplayer Mode

### Scenario 6.1: Alternate turns between two players on the same device
**Given** a local multiplayer game has been started  
**When** player 1 makes a valid move  
**Then** the turn should pass to player 2  
**And** the turn indicator should reflect that it is now player 2’s turn  
**And** this behavior should continue, alternating turns until the game ends.

### Scenario 6.2: Display the result to both players
**Given** the local multiplayer game has ended  
**When** the game detects a winner  
**Then** it should display who won (player 1 or player 2, or "X" / "O")  
**And** both players should be able to clearly see the result on the screen.

---

## 7. Play Against the Computer (AI)

### Scenario 7.1: Select play against the computer
**Given** the user is on the game start screen  
**When** the user selects the "Play against the computer" mode  
**Then** the game should be configured so that one player is human and the other is controlled by the AI  
**And** it should be clearly indicated which player is human and which is the computer.

### Scenario 7.2: Computer’s turn
**Given** the game is in play-against-the-computer mode  
**And** the human player has made a valid move  
**When** the human player’s turn ends  
**Then** the computer should automatically make a valid move on the board  
**And** after the computer’s move, the turn should return to the human player.

### Scenario 7.3: AI difficulty (when applicable)
**Given** the game offers different difficulty levels for the computer (for example: easy, medium, hard)  
**When** the user selects a difficulty level before starting the game  
**Then** the AI’s behavior should adapt to the selected difficulty  
**And** the gameplay experience should feel easier or more challenging based on that selection.

---
