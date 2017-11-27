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
- `+` `// rows1 == rows2 && columns1 == columns2`
- `-` `// rows1 == rows2 && columns1 == columns2`
- `*` `// columns1 == rows2`
- `T` - транспонирование
- `R` - нахождение обратной матрицы `// rows == columns`

### Подсказка
```
bool equal( float ** lhs_elements,
            unsigned int lhs_rows,
            unsigned int lhs_columns,
            float ** rhs_elements,
            unsigned int rhs_rows,
            unsigned int rhs_columns );

bool add( float ** lhs_elements,
          unsigned int lhs_rows,
          unsigned int lhs_columns,
          float ** rhs_elements,
          unsigned int rhs_rows,
          unsigned int rhs_columns,
          float ** & result_elements,
          unsigned int & result_rows,
          unsigned int & result_columns );

bool sub( float ** lhs_elements,
          unsigned int lhs_rows,
          unsigned int lhs_columns,
          float ** rhs_elements,
          unsigned int rhs_rows,
          unsigned int rhs_columns,
          float ** & result_elements,
          unsigned int & result_rows,
          unsigned int & result_columns );

bool multiply( float ** lhs_elements,
               unsigned int lhs_rows,
               unsigned int lhs_columns,
               float ** rhs_elements,
               unsigned int rhs_rows,
               unsigned int rhs_columns,
               float ** & result_elements,
               unsigned int & result_rows,
               unsigned int & result_columns );

auto input( std::istream & stream, 
            float ** & result_elements, 
            unsigned int & result_rows, 
            unsigned int & result_columns ) -> std::istream &;

bool transpose( float ** lhs_elements,
                unsigned int lhs_rows,
                unsigned int lhs_columns,
                float ** & result_elements,
                unsigned int & result_rows,
                unsigned int & result_columns );

void destroy( float ** elements,
              unsigned int rows )
{
    for( unsigned int i = 0; i < rows; ++i ) {
        delete [] elements[ i ];
    }
    delete [] elements; 
}

auto create( unsigned int rows,
             unsigned int columns,
             float filler = 0.0f ) -> float **
{
    float ** elements = new float *[ rows ];
    for( unsigned int i = 0; i < rows; ++i ) {
        elements[ i ] = new float[ columns ];
        for( unsigned int j = 0; j < columns; ++j ) {
            elements[ i ][ j ] = filler;
        }
    }
    
    return elements;
}

bool truncate( float ** lhs_elements,
               unsigned int lhs_rows,
               unsigned int lhs_columns,
               unsigned int new_rows,
               unsigned int new_columns,
               unsigned int start_row_index,
               unsigned int start_colmn_index,
               float ** & result_elements,
               unsigned int & result_rows,
               unsigned int & result_columns );

auto output( std::ostream & stream, 
             float ** elements, 
             unsigned int rows, 
             unsigned int columns ) -> std::ostream &;

bool reverse( float ** lhs_elements,
              unsigned int lhs_rows,
              unsigned int lhs_columns,
              float ** & result_elements,
              unsigned int & result_rows,
              unsigned int & result_columns );
```

### Входные данные
Во входных данных заданы строки, следующего формата:
```
<rows1, columns1>
<число> <число>
<число> <число>
<число> <число>
<бинарная операция>
<rows2, columns2>
<число> <число>
<число> <число>
<число> <число>
```
```
<rows, columns>
<число> <число> <число>
<число> <число> <число>
<унарная операция>
```
### Выходные данные
Результат арифмитической операции или строка, сведетельствующая о возникновении ошибки:
- `An error has occured while reading input data`
- `There is no reverse matrix`

### Примеры
#### входные данные
```
3, 3
2 2 2
2 2 2
2 2 2
+
3, 3
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
3, 3
2 2 2
2 2 2
2 2 2
-
3, 3
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
3, 3
2 2 2
2 2 2
2 2 2
*
3, 3
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
3, 3
1 2 2
0 4 4
0 4 0
R
```
#### выходные данные
```
1 -0.5  0
0 0 0.25
0 0.25 -0.25
```
#### входные данные
```
3, 3
1 2 3
4 5 6
7 8 9
R
```
#### выходные данные
```
There is no reverse matrix
```
#### входные данные
```
3, 2
2 2
2 2
2 2
T
```
#### выходные данные
```
2 2 2
2 2 2
```
#### входные данные
```
3, 3
2 2 2
2 2
2 2 2
+
2, 3
1 1 1
1 1 1
```
#### выходные данные
```
An error has occured while reading input data
```

# matrix@0.0.3

### Задание
Написать программу, выполняющую арифмитические операции над **динамическими** матрицами. Программа должна поддерживать следующие операции:
- `+` `// rows1 == rows2 && columns1 == columns2`
- `-` `// rows1 == rows2 && columns1 == columns2`
- `*` `// columns1 == rows2`
- `T` - транспонирование
- `R` - нахождение обратной матрицы `// rows == columns`

### Входные данные
Во входных данных заданы строки, следующего формата:
```
<имя файла, содержащего размеры 1-ой матрицы и ее элементы> <бинарная операция> <имя файла, содержащего размеры 2-ой матрицы и ее элементы>
```
```
<имя файла, содержащего размеры матрицы и ее элементы> <унарная операция>
```
### Выходные данные
Результат арифмитической операции или строка, сведетельствующая о возникновении ошибки:
- `An error has occured while reading input data`
- `There is no reverse matrix`

### Примеры
```
A.txt
3, 3
2 2 2
2 2 2
2 2 2
```
```
B.txt
3, 3
1 1 1
1 1 1
1 1 1
```
```
C.txt
3, 3
1 2 2
0 4 4
0 4 0
```
```
D.txt
3, 3
1 2 3
4 5 6
7 8 9
```
#### входные данные
```
A.txt + B.txt
```
#### выходные данные
```
3 3 3
3 3 3
3 3 3
```
#### входные данные
```
A.txt - B.txt
```
#### выходные данные
```
1 1 1
1 1 1
1 1 1
```
#### входные данные
```
A.txt * B.txt
```
#### выходные данные
```
6 6 6
6 6 6
6 6 6
```
#### входные данные
```
C.txt R
```
#### выходные данные
```
1 -0.5  0
0 0 0.25
0 0.25 -0.25
```
#### входные данные
```
D.txt R
```
#### выходные данные
```
There is no reverse matrix
```
#### входные данные
```
D.txt T
```
#### выходные данные
```
1 4 7
2 5 8
3 6 9
```
