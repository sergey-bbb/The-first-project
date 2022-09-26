# the_first_project

tictactoe = [1, 2, 3,
             4, 5, 6,
             7, 8, 9]

# Победа
victories = [[0, 1, 2],
             [3, 4, 5],
             [6, 7, 8],
             [0, 3, 6],
             [1, 4, 7],
             [2, 5, 8],
             [0, 4, 8],
             [2, 4, 6]]

# Вывод карты на экран
def print_tictactoe():
    print(tictactoe[0], end=" ")
    print(tictactoe[1], end=" ")
    print(tictactoe[2])

    print(tictactoe[3], end=" ")
    print(tictactoe[4], end=" ")
    print(tictactoe[5])

    print(tictactoe[6], end=" ")
    print(tictactoe[7], end=" ")
    print(tictactoe[8])


# Сделать ход в ячейку
def step_tictactoe(step, symbol):
    ind = tictactoe.index(step)
    tictactoe[ind] = symbol


# Получить текущий результат игры
def get_result():
    win = ""

    for i in victories:
        if tictactoe[i[0]] == "X" and tictactoe[i[1]] == "X" and tictactoe[i[2]] == "X":
            win = "X"
        if tictactoe[i[0]] == "O" and tictactoe[i[1]] == "O" and tictactoe[i[2]] == "O":
            win = "O"

    return win

# Ключевая логика
game_over = False
player1 = True

while game_over == False:

    # Карта
    print_tictactoe()

    # Ход игры
    if player1 == True:
        symbol = "X"
        step = int(input("Человек 1, ваш ход: "))
    else:
        symbol = "O"
        step = int(input("Человек 2, ваш ход: "))

    step_tictactoe(step, symbol)  # делаем ход в указанную ячейку
    win = get_result()  # определим победителя
    if win != "":
        game_over = True
    else:
        game_over = False

    player1 = not (player1)

# Игра окончена
print_tictactoe()
print("Победa", win)
