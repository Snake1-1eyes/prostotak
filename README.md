# Анализ волнового алгоритма

## Временная сложность и практические измерения

| Часть алгоритма | Временная сложность | Время выполнения (сек) | Описание |
|-----------------|---------------------|----------------------|-----------|
| Подсчет вершин | O(E) | 0.000005 | Проход по всем ребрам графа для подсчета уникальных вершин |
| Получение списка вершин | O(E) | 0.000002 | Формирование списка уникальных вершин из ребер |
| Обход вершин | O(V * E) | 0.000015 | Поиск кратчайшего пути волновым алгоритмом |
| Восстановление пути | O(V) | 0.000004 | Восстановление найденного пути от конечной до начальной вершины |

где V - количество вершин, E - количество ребер

## Входные данные
```python
edges = [(1, 2), (2, 3), (2, 4), (4, 5), (1, 6), (6, 7), (4, 5)]
start = 1
end = 5
```

## Тестовый стенд
```python
import time

def measure_execution_time(func, *args):
    start_time = time.perf_counter()
    result = func(*args)
    end_time = time.perf_counter()
    return result, end_time - start_time

# Примеры использования для каждой функции:

# 1. Подсчет вершин
vertices_count, count_time = measure_execution_time(count_vertices, edges)
print(f"Подсчет вершин: количество = {vertices_count}, время = {count_time:.6f} сек")

# 2. Получение списка вершин
vertices_list, list_time = measure_execution_time(get_vertices, edges)
print(f"Список вершин: вершины = {vertices_list}, время = {list_time:.6f} сек")

# 3. Выполнение волнового алгоритма (обход вершин)
path, visited, traverse_time, path_time = measure_execution_time(wave_algorithm, edges, start, end)
print(f"Обход вершин: время = {traverse_time:.6f} сек")

# 4. Восстановление пути
if path:
    print(f"Восстановление пути: путь = {path}, время = {path_time:.6f} сек")
else:
    print("Путь не найден")
```
# Анализ алгоритма поиска второго минимального элемента

## Временная сложность и практические измерения

| Часть алгоритма | Временная сложность | Время выполнения (сек) | Описание |
|-----------------|---------------------|----------------------|-----------|
| Поиск второго минимума | O(n) | 0.000004 | Однократный проход по массиву для поиска второго минимального элемента |

где n - количество элементов в массиве

## Входные данные
```python
test_array = [5, 2, 8, 1, 9]
```

## Тестовый стенд
```python
import time

def measure_execution_time(func, *args):
    start_time = time.perf_counter()
    result = func(*args)
    end_time = time.perf_counter()
    return result, end_time - start_time

# Пример использования
result, exec_time = measure_execution_time(find_second_min, test_array)
print(f"Массив: {test_array}")
print(f"Второй минимум: {result}")
print(f"Время выполнения: {exec_time:.6f} сек\n")
```
