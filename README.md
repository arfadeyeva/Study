# убирает первый и последний символ
def remove_char(s):
    return s[1:-1] if len(s) > 2 else ''

# расставляет запятые в числе в соответсвии с американской системой

str_number = str(input())
length = len(str_number)
first_numbers = length % 3
iterations = length // 3
if first_numbers == 0 :
    build_in = str_number[:3]
    start = 3
    end = start + 3
    iterations -= 1
else:
    build_in = str_number[:first_numbers]
    start = first_numbers
    end = first_numbers + 3
for i in range(iterations):
    build_in = build_in + "," + str_number[start:end]
    start = end
    end = start + 3
print(build_in)


# функция получает количество точек и дальше их координаты и считает, сколько из них находятся в какой четверти
координатной плоскости

def which_quadrant():
    quantity = int(input())
    first_quadrant = 0
    second_quadrant = 0
    third_quadrant = 0
    fourth_quadrant = 0
    for i in range(int(quantity)):
        coordinats = input()
        coordinats = coordinats.split()
        x = int(coordinats[0])
        y = int(coordinats[1])
        if x == 0 or y == 0:
            continue
        elif x > 0 and y > 0:
            first_quadrant += 1
        elif  x < 0 < y:
            second_quadrant += 1
        elif x < 0 and y < 0:
            third_quadrant += 1
        else:
            fourth_quadrant += 1
    print(f'''Первая четверть: {first_quadrant}
    Вторая четверть: {second_quadrant}
    Третья четверть: {third_quadrant}
    Четвертая четверть: {fourth_quadrant}''')

which_quadrant()

# функция принимает строку из чисел и считает, сколько из чисел в этой строке были больше, чем предыдущее

def how_much_is_bigger():
    list = input()
    arr_list = list.split()
    len_arr_list = len(arr_list)
    counter = 0
    for i in range(len_arr_list - 1):
        first_i = int(arr_list[i])
        second_i = int(arr_list[i + 1])
        if int(first_i) < int(second_i):
            counter += 1
    print(counter)

how_much_is_bigger()

# функция меняет местами пары чисел в ряду, если число чисел в ряду нечетное - последнее остается на месте

def twins_changer():
    arr_list = input().split()
    len_arr_list = len(arr_list)
    storage = ''
    first_i = 0
    second_i = 1
    for i in range(len_arr_list // 2):
        changer = f'{arr_list[second_i]} {arr_list[first_i]} '
        storage += changer
        first_i += 2
        second_i += 2
    if not (len_arr_list % 2) == 0:
        storage += arr_list[-1]
    print(storage)

twins_changer()

# циклический сдвиг по индексу в большую сторону

def cycle_rotater(n=1):
    arr_list = input().split()
    storage = str(arr_list[-1])
    for a in range(n):
        for i in range(len(arr_list) - 1):
            storage = f'{storage} {arr_list[i]}'
    print(storage)

cycle_rotater()

# считает количество отличающихся элементов в строке из ряда чисел, разположенных по неубыванию

def difference_counter():
    arr_list = input().split()
    counter = 1
    for i in range(len(arr_list) - 1):
        if arr_list[i] != arr_list[i + 1]:
            counter += 1
    print(counter)

difference_counter()

# функция для определения, является ли число произведением двух чисел из данного набора.
# на вход: 1 строка - кол-во чисел, 2 - ... строка  - числа, последняя строка - произведение

def is_product():
    how_much_number = int(input())
    number_str = ''
    for i in range(how_much_number):
        number = input()
        number_str = f'{number_str} {number}'
    number_arr = number_str.split()
    probably_product = input()
    is_product = 'НЕТ'
    for a in range(how_much_number-1):
        if is_product == 'ДА':
            break
        for b in range(how_much_number):
            if b == a:
                continue
            else:
                prod = int(number_arr[a]) * int(number_arr[b])
                if prod == int(probably_product):
                    is_product = 'ДА'
                    break
        a = a + 1
    print(is_product)

is_product()


# игра камень ножницы бумага между тимуром и русланом

def who_is_winning():
    timur = input()
    ruslan = input()
    if timur == ruslan:
        print("ничья")
    elif timur == "ножницы":
        if ruslan == "бумага":
            print("Тимур")
        else:
            print("Руслан")
    elif timur == "бумага":
        if ruslan == "ножницы":
            print("Руслан")
        else:
            print("Тимур")
    else:
        if ruslan == "ножницы":
            print("Тимур")
        else:
            print("Руслан")

who_is_winning()

#более сложная версия (с ячерицей и Споком)

ef who_is_winning():
    timur = input()
    ruslan = input()
    if timur == ruslan:
        print("ничья")
    elif timur == "ножницы":
        if ruslan in ("бумага", "ящерица"):
            print("Тимур")
        else:
            print("Руслан")
    elif timur == "бумага":
        if ruslan in ("ножницы", "ящерица"):
            print("Руслан")
        else:
            print("Тимур")
    elif timur == "камень":
        if ruslan in ("ящерица", "ножницы"):
            print("Тимур")
        else:
            print("Руслан")
    elif timur == "ящерица":
        if ruslan in ("Спок", "бумага"):
            print("Тимур")
        else:
            print("Руслан")
    else:
        if ruslan in ("ножницы", "камень"):
            print("Тимур")
        else:
            print("Руслан")
who_is_winning()
