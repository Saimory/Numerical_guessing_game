# Numerical_guessing_game
from random import *

print("Добро пожаловать в числовую угадайку")


def is_valid(number):
    if number.isdigit():
        return peak >= int(number) >= 1
    else:
        return False


def yes_not(ans):
    return ans.lower() == 'да'


while True:
    print('До какого числа желаете погадать ?')
    print('Введите желаемое максимальное число которое может вообще загадаться: ')
    peak = int(input())
    ran = randrange(1, peak + 1)
    print('Как думаете какое число я загадал ?')
    kol = 0
    while True:
        num = input()
        if is_valid(num):
            num = int(num)
        else:
            print(f'А может быть все-таки введем целое число от 1 до {peak}?')
            continue

        if num > ran:
            print('Ваше число больше загаданного, попробуйте еще разок')
            kol += 1
        elif num < ran:
            print('Ваше число меньше загаданного, попробуйте еще разок')
            kol += 1
        else:
            print('Вы угадали, поздравляем!')
            print(f"Вам удалось это сделать все за: {kol} попыток")
            print('Спасибо, что играли в числовую угадайку. Еще свидимся...')
            break
    print('Сыграем еще разок ?, Да/Нет')
    answer = input()
    if yes_not(answer):
        print("Ну и хорошо, продолжаем што ли...")
        continue
    else:
        print("Ну и ладно...Как хотите")
        break
