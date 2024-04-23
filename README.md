def binary_search(array, element, left, right):
    """
    Реализация алгоритма двоичного поиска
    """
    while left <= right:
        middle = (left + right) // 2
        if array[middle] < element:
            left = middle + 1
        elif array[middle] > element:
            right = middle - 1
        else:
            return middle
    return left

def sort_list(sequence):
    """
    Функция сортировки списка
    """
    sequence.sort()

def main():
    # Ввод последовательности чисел
    sequence = input("Введите последовательность чисел через пробел: ").split()
    try:
        # Преобразование введённой последовательности в список чисел
        sequence = list(map(int, sequence))
    except ValueError:
        print("Ошибка: Последовательность должна состоять из целых чисел.")
        return
    
    # Ввод числа от пользователя
    try:
        number = int(input("Введите число для поиска: "))
    except ValueError:
        print("Ошибка: Введено некорректное число.")
        return
    
    # Сортировка списка
    sort_list(sequence)

    # Поиск позиции элемента
    position = binary_search(sequence, number, 0, len(sequence) - 1)
    
    # Вывод результата
    if position == len(sequence):
        print(f"Число {number} больше всех чисел в последовательности.")
    else:
        print(f"Позиция числа {number} в отсортированной последовательности: {position}")


if __name__ == "__main__":
    main()
