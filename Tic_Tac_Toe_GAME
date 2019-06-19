# TIC TAC TOE GAME
# 6/11/19

# Will conduct the turn based on player
def doTheTurn(board, boolBoard, player, xTurn):
    validInput = False
    row = 0
    column = 0
    indices = [0,0]
    while not validInput:
            row = input(player + ", Please select a row where you wish to place your mark(type 0, 1, or 2)")
            column = input(player + ", Please select a column where you wish to place your mark(type 0, 1, or 2)")
            # Tests whether or not it's an integer; tries to cast it as an int; if it doesn't work it will
            # throw an exception.
            try:
                val = int(row)
                val2 = int(column)
                if (val >= 0 and val <= 2 and val2 >= 0 and val2 <= 2):
                    if (boolBoard[val][val2] != False):
                        print("That space is occupied.")
                    else:
                        boolBoard[val][val2] = True
                        if xTurn:
                            board[val][val2] = "X"
                        else:
                            board[val][val2] = "O"
                        validInput = True
                else:
                    print("Invalid Index; must be between 0 and 2")
            except ValueError:
                print("Invalid output; not an integer.")
        # Checks if it's feasible to be put into a matrix

# Helper method; checks row
def checkRows(board):
    if ("X" == board[0][0] == board[0][1] == board[0][2] or "O" == board[0][0] == board[0][1] == board[0][2]):
        return True
    elif ("X" == board[1][0] == board[1][1] == board[1][2] or "O" == board[1][0] == board[1][1] == board[1][2]):
        return True
    elif ("X" == board[2][0] == board[2][1] == board[2][2] or "O" == board[2][0] == board[2][1] == board[2][2] ):
        return True
    return False

# Helper method; checks column
def checkCols(board):
    if ("X" == board[0][0] == board[1][0] == board[2][0] or "O" == board[0][0] == board[1][0] == board[2][0]):
        return True
    elif ("X" == board[0][1] == board[1][1] == board[2][1] or "O" == board[0][1] == board[1][1] == board[2][1]):
        return True
    elif ("X" == board[0][2] == board[1][2] == board[2][2] or "O" == board[0][2] == board[1][2] == board[2][2]):
        return True
    return False
    
# Helper method; checks diagonal
def checkDia(board):
    if ("X" == board[0][0] == board[1][1] == board[2][2] or "O" == board[0][0] == board[1][1] == board[2][2]):
        return True
    elif ("X" == board[2][0] == board[1][1] == board[0][2] or "O" == board[2][0] == board[1][1] == board[0][2]):
        return True
    return False

# Will check the board each turn; rows, columns, diagonals, and returns true if conditions are met.
def checkBoard(board):
    if checkRows(board):
        return True
    elif checkCols(board):
        return True
    elif checkDia(board):
        return True
    return False

# Displays the board
def printBoard(board):
    for i in range(len(board)):
        for j in range(len(board[i])):
            print(board[i][j], end=' ')
        print()

# Creates and initializes the board
def tic_tac_toe():
    board = [['-', '-', '-'], ['-', '-', '-'], ['-', '-', '-']]
    boolBoard = [[False, False, False], [False, False, False], [False, False, False]]
    gameDone = False
    xTurn = True
    winner = ""
    printBoard(board)
    count = 0
    playerOne = input("Player One, enter your name: ")
    playerTwo = input("Player Two, enter your name: ")
    while not gameDone:
        doTheTurn(board, boolBoard, playerOne, True)
        count += 1
        printBoard(board)
        if checkBoard(board):
            gameDone = True
            winner = playerOne
            break
        if (count == 9):
            gameDone = True
            break
        doTheTurn(board, boolBoard, playerTwo, False)
        count += 1
        printBoard(board)
        if checkBoard(board):
            gameDone = True
            winner = playerTwo
            break
        if count == 9:
            gameDone = True
            break
    print(winner + " is the winner!")
    ans = input("Play Again? Y/N")
    if ans == "Y" or ans == "y" or ans == "yes" or ans == "Yes":
        tic_tac_toe()
    else:
        print("Thank you for your time!")

def main_method():
    tic_tac_toe()

if __name__ == '__main__':
    main_method()
