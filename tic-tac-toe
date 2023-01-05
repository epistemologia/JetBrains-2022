# write your code here

mat = [[' ' for i in range(3)] for j in range(3)]
simbolo = ' '
fim_jogo = False

def limpa_matriz():
    mat = [[' ' for i in range(3)] for j in range(3)]
    return


def matrix_open():
    print("---------")
    return


def out_line(linha):
    global mat
    # linha entre 0 e 2
    temp = "| "
    temp = temp + mat[linha] [0] + " "
    temp = temp + mat[linha] [1] + " "
    temp = temp + mat[linha] [2] + " "
    temp = temp + "|"
    print(temp)
    return


def matrix_print():
    matrix_open()
    for i in range(3):
        out_line(i)
    matrix_close()
    return


def matrix_close():
    print("---------")
    return


def verifica_vitoria(lado):
    # conta linhas vencidas pelo lado informado
    global mat
    linhas = 0
    if mat[0][0] == mat[1][1] and mat[1][1] == mat[2][2]:
        if mat[0][0] == lado:
            linhas += 1
    if mat[0][2] == mat[1][1] and mat[1][1] == mat[2][0]:
        if mat[0][2] == lado:
            linhas += 1
    for i in range(3):
        if mat[i][0] == lado and mat[i][0] == mat[i][1] and mat[i][1] == mat[i][2]:
            linhas += 1
        if mat[0][i] == lado and mat[0][i] == mat[1][i] and mat[1][i] == mat[2][i]:
            linhas += 1
    return linhas


def matrix_analysis():
    global mat, fim_jogo
    resultado = "Game not finished"
    num_x = 0
    num_o = 0
    empty = 0
    vence_x = 0
    vence_o = 0
    for i in range(3):
        for j in range(3):
            temp = mat[i][j]
            if (temp == ' ') or (temp == '_'):
                empty += 1
            if temp == 'O':
                num_o += 1
            if temp == 'X':
                num_x += 1
    vence_o = verifica_vitoria('O')
    vence_x = verifica_vitoria('X')
    if vence_x >= 1 and vence_o == 0:
        resultado = "X wins"
        fim_jogo = True
    if vence_o >= 1 and vence_x == 0:
        resultado = "O wins"
        fim_jogo = True
    if (empty == 0) and (vence_x + vence_o == 0):
        resultado = "Draw"
        fim_jogo = True

    if (abs(num_o - num_x) > 1) or (vence_o + vence_x > 1):
        resultado = "Impossible"
    return resultado


def make_move():
    global mat, simbolo
    a = 0
    b = 0
    while a-1 not in range(3) or b-1 not in range(3):
        try:
            temp = input()
            temp2 = temp.split()
            a, b = int(temp2[0]), int(temp2[1])
        except Exception:
            print("You should enter numbers!")
            a = 99
            continue
        else:
            if a-1 not in range(3) or b-1 not in range(3):
                print("Coordinates should be from 1 to 3!")
                continue
            elif mat[a-1][b-1] in ['O', 'X']:
                print("This cell is occupied! Choose another one!")
                a = 99
                continue
        finally:
            continue
    mat[a-1][b-1] = simbolo
    return



# line = input()

fim_jogo = False
equipe = 0
simbolos = ['O', 'X']
limpa_matriz()
matrix_print()  # Start with blank matrix

while not fim_jogo:
    equipe = 1 - equipe  # Alterna entre O e X
    simbolo = simbolos[equipe]  # Switches character
    make_move()  # Works for both teams in alternance
    matrix_print()
    resultado = matrix_analysis()
print(resultado)
