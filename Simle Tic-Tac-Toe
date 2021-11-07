# write your code here
string = '_________'


def pole():
    global string
    flag = False
    string_print = ''
    count = 0
    print('---------')
    for i in string:
        if count == 0:
            string_print += '| '
        count += 1
        string_print += i
        string_print += ' '
        if count == 3:
            string_print += '|'
            print(string_print)
            string_print = ''
            count = 0
    print('---------')

def scanner():
    global string
    x1 = string[:3] == 'X' * 3
    x2 = string[3:6] == 'X' * 3
    x3 = string[6:-1] == 'X' * 3
    x4 = string[0::4] == 'X' * 3
    x5 = string[2:7:2] == 'X' * 3
    x6 = string[0:8:3] == 'X' * 3
    x7 = string[1:9:3] == 'X' * 3
    x8 = string[2::3] == 'X' * 3
    x_variant = [x1, x2, x3, x4, x5, x6, x7, x8]

    o1 = string[:3] == 'O' * 3
    o2 = string[3:6] == 'O' * 3
    o3 = string[6:-1] == 'O' * 3
    o4 = string[0::4] == 'O' * 3
    o5 = string[2:7:2] == 'O' * 3
    o6 = string[0:8:3] == 'O' * 3
    o7 = string[1:9:3] == 'O' * 3
    o8 = string[2::3] == 'O' * 3
    o_variant = [o1, o2, o3, o4, o5, o6, o7, o8]

    if string.count('X') - string.count('O') < -1 or string.count('X') - string.count('O') > 1:
        print('Impossible')
        return True
    elif True in x_variant and not True in o_variant:
        print('X wins')
        return False
    elif True in o_variant and not True in x_variant:
        print('O wins')
        return False
    elif True in x_variant and True in o_variant:
        print('Impossible')
        return True
    elif not '_' in string:
        print('Draw')
        return False
    else:
        print('Game not finished')
        return True


def step():
    xo = 'XO'
    count = 0
    x = True
    global string
    pole()
    while x == True:
        coordinat = input('Enter the coordinates:').split()
        coordinat = [int(i) for i in coordinat]
        if not str(coordinat[0]).isdigit() or not str(coordinat[1]).isdigit():
            print('You should enter numbers!')
        elif 1 > coordinat[0] > 3 or 1 > coordinat[1] > 3:
            print('Coordinates should be from 1 to 3!')
        elif coordinat[0] == 1:
            if string[0 + coordinat[1] - 1] in xo:
                print('This cell is occupied! Choose another one!')
            else:
                string = string[0:0 + coordinat[1] - 1] + (xo[count % 2]) + string[0 + coordinat[1]:]
                pole()
                count += 1
        elif coordinat[0] == 2:
            if string[3 + coordinat[1] - 1] in xo:
                print('This cell is occupied! Choose another one!')
            else:
                string = string[0:3 + coordinat[1] - 1] + (xo[count % 2]) + string[3 + coordinat[1]:]
                pole()
                count += 1
        elif coordinat[0] == 3:
            if string[6 + coordinat[1] - 1] in xo:
                print('This cell is occupied! Choose another one!')
            elif coordinat[1] == 3:
                string = string[0:6 + coordinat[1] - 1] + (xo[count % 2])
                pole()
                count += 1
            else:
                string = string[0:6 + coordinat[1] - 1] + (xo[count % 2]) + string[6 + coordinat[1]:]
                pole()
                count += 1
        x = scanner()
    return scanner()

step()
