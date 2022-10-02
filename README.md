# Python-3
# Задайте список из нескольких чисел. Напишите программу, 
# которая найдёт сумму элементов списка, стоящих на нечётной позиции.
# Пример:
# - [2, 3, 5, 9, 3] -> на нечётных позициях элементы 3 и 9, ответ: 12


x = [99, 2, 67, 6, 12]

sum = 0
for i in range(1, len(x), 2):
    sum += x[i]       
print(f"{x} сумма элементов на нечётных позициях: {sum}")

#Напишите программу, которая найдёт произведение пар чисел списка. Парой считаем первый и последний элемент, второй и предпоследний и т.д.
#Пример:
#- [2, 3, 4, 5, 6] => [12, 15, 16];
#- [2, 3, 5, 6] => [12, 15]
def mult_lst(lst):
    l = len(lst)//2 + 1 if len(lst) % 2 != 0 else len(lst)//2
    new_lst = [lst[i]*lst[len(lst)-i-1] for i in range(l)]
    print(new_lst)

lst = [2, 3, 4, 5, 6]
mult_lst(lst)
lst = list(map(int, input("Введите числа через пробел:\n").split()))
mult_lst(lst)

#Задайте список из вещественных чисел. Напишите программу, которая найдёт разницу между максимальным и минимальным значением дробной части элементов.
#Пример:
#- [1.1, 1.2, 3.1, 5, 10.01] => 0.19
my_list = [1.1, 1.2, 3.1, 5, 10.01]
min = 1
max = 0
for i in my_list:
    if (i - int(i)) <= min:
        min = i - int(i)
    if (i - int(i)) >= max:
        max = i - int(i)  
print(max-min)

#Напишите программу, которая будет преобразовывать десятичное число в двоичное.
#Пример:
#- 45 -> 101101
#- 3 -> 11
#- 2 -> 10
n = int(input('Введите число: ')) 
b = ''
while n > 0:
    b = str(n % 2) + b
    n = n // 2
print(f'В двоичной системе: {b}')

#Задайте число. Составьте список чисел Фибоначчи, в том числе для отрицательных индексов.
n = int(input('Введите число: '))

def get_fibonacci(n):
    fibo_num = []
    a, b = 1, 1
    for i in range(n-1):
        fibo_num.append(a)
        a, b = b, a + b
    a, b = 0, 1
    for i in range (n):
        fibo_num.insert(0, a)
        a, b = b, a - b
    return fibo_num

fibo_num = get_fibonacci(n)
print(get_fibonacci(n))
print(fibo_num.index(0))

или с рекурсией:
def fibonacci(n):
    if n == 1 or n == 2:
        return 1
    return fibonacci(n - 1) + fibonacci(n - 2)


n = int(input())
print(fibonacci(n))


















