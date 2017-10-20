# matrix@0.0.1

### Задание
Написать программу, выполняющую арифмитические операции над статическими матрицами размеров **3*****3**. Программа должна поддерживать следующие операции:
- `+`
- `-`
- `*`

### Замечания
Для реализации статических матриц использовать двумерные массивы вида `int matrix[3][3]`.

### Входные данные
Во входных данных заданы строки, следующего формата:
```
<число> <число> <число>
<число> <число> <число>
<число> <число> <число>
<операция>
<число> <число> <число>
<число> <число> <число>
<число> <число> <число>
```

### Выходные данные
Результат арифмитической операции или строка `An error has occured while reading input data`, сведетельствующая о возникновении ошибки ввода.

### Примеры
#### входные данные
```
2 2 2
2 2 2
2 2 2
+
1 1 1
1 1 1
1 1 1
```
#### выходные данные
```
3 3 3
3 3 3
3 3 3
```
#### входные данные
```
2 2 2
2 2 2
2 2 2
-
1 1 1
1 1 1
1 1 1
```
#### выходные данные
```
1 1 1
1 1 1
1 1 1
```
#### входные данные
```
2 2 2
2 2 2
2 2 2
*
1 1 1
1 1 1
1 1 1
```
#### выходные данные
```
6 6 6
6 6 6
6 6 6
```
#### входные данные
```
2 2 2
2 2 2
2 2 2
+
1 1 1
1 1 1
```
#### выходные данные
```
An error has occured while reading input data
```

# matrix@0.0.2

### Задание
Написать программу, выполняющую арифмитические операции над **динамическими** матрицами. Программа должна поддерживать следующие операции:
- `+`
- `-`
- `*`

### Входные данные
Во входных данных заданы строки, следующего формата:
```

<число> <число> <число>
<число> <число> <число>
<число> <число> <число>

<операция>

<число> <число> <число>
<число> <число> <число>
<число> <число> <число>

```

### Выходные данные
Результат арифмитической операции или строка `An error has occured while reading input data`, сведетельствующая о возникновении ошибки ввода.

### Примеры
#### входные данные
```
2 2 2
2 2 2
2 2 2

+

1 1 1
1 1 1
1 1 1

```
#### выходные данные
```
3 3 3
3 3 3
3 3 3
```
#### входные данные
```
2 2 2
2 2 2
2 2 2

-

1 1 1
1 1 1
1 1 1

```
#### выходные данные
```
1 1 1
1 1 1
1 1 1
```
#### входные данные
```
2 2 2
2 2 2
2 2 2

*

1 1 1
1 1 1
1 1 1

```
#### выходные данные
```
6 6 6
6 6 6
6 6 6
```
#### входные данные
```
2 2 2
2 2
2 2 2

+

1 1 1
1 1 1

```
#### выходные данные
```
An error has occured while reading input data
```
