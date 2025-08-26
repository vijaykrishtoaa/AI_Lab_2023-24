# Ex.No: 3  Implementation of Minimax Search
### DATE:                                                                            
### REGISTER NUMBER : 
### AIM: 
Write a mini-max search algorithm to find the optimal value of MAX Player from the given graph.
### Algorithm:
1. Start the program
2. import the math package
3. Specify the score value of leaf nodes and find the depth of binary tree from leaf nodes.
4. Define the minimax function
5. If maximum depth is reached then get the score value of leaf node.
6. Max player find the maximum value by calling the minmax function recursively.
7. Min player find the minimum value by calling the minmax function recursively.
8. Call the minimax function  and print the optimum value of Max player.
9. Stop the program. 

### Program:
import math

# Function to check winner or tie
def evaluate(board):
    # Check rows
    for row in board:
        if row.count(row[0]) == 3 and row[0] != "_":
            return 10 if row[0] == "X" else -10
    
    # Check columns
    for col in range(3):
        if board[0][col] == board[1][col] == board[2][col] and board[0][col] != "_":
            return 10 if board[0][col] == "X" else -10
    
    # Check diagonals
    if board[0][0] == board[1][1] == board[2][2] and board[0][0] != "_":
        return 10 if board[0][0] == "X" else -10
    if board[0][2] == board[1][1] == board[2][0] and board[0][2] != "_":
        return 10 if board[0][2] == "X" else -10
    
    return 0  # No winner yet

# Check if moves left
def is_moves_left(board):
    for row in board:
        if "_" in row:
            return True
    return False

# Minimax function
def minimax(board, depth, is_max):
    score = evaluate(board)

    # If maximizer has won
    if score == 10:
        return score - depth

    # If minimizer has won
    if score == -10:
        return score + depth

    # If no moves left
    if not is_moves_left(board):
        return 0

    if is_max:  # Maximizing player
        best = -math.inf
        for i in range(3):
            for j in range(3):
                if board[i][j] == "_":
                    board[i][j] = "X"
                    best = max(best, minimax(board, depth + 1, False))
                    board[i][j] = "_"
        return best
    else:  # Minimizing player
        best = math.inf
        for i in range(3):
            for j in range(3):
                if board[i][j] == "_":
                    board[i][j] = "O"
                    best = min(best, minimax(board, depth + 1, True))
                    board[i][j] = "_"
        return best

# Find best move for X
def find_best_move(board):
    best_val = -math.inf
    best_move = (-1, -1)

    for i in range(3):
        for j in range(3):
            if board[i][j] == "_":
                board[i][j] = "X"
                move_val = minimax(board, 0, False)
                board[i][j] = "_"
                if move_val > best_val:
                    best_move = (i, j)
                    best_val = move_val

    return best_move

# Example board state
board = [
    ["X", "O", "X"],
    ["O", "O", "_"],
    ["_", "_", "X"]
]

print("Current board state:")
for row in board:
    print(row)

best_move = find_best_move(board)
print("\nThe best move for X is:", best_move)











### Output:
Current board state:
['X', 'O', 'X']
['O', 'O', '_']
['_', '_', 'X']

The best move for X is: (1, 2)



### Result:
Thus the optimum value of max player was found using minimax search.
