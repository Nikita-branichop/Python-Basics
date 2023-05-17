# Задача 1 - Numbers from 1 to 100

Напишете програма, която отпечатва числата от 1 до 100, всяко на нов ред.

```python
for i in range(1, 101, 1):
    print(i)
```

---
# Задача 2 - Numbers 1...N with Step 3

Напишете програма, която чете число n, въведено от потребителя и отпечатва числата от 1 до n през 3.

```python
n = int(input())
for i in range(1, n + 1, 3):
    print(i)
```

---
# Задача 3 - Even Powers of 2

Да се напише програма, която чете число n, въведено от потребителя, и печата четните степени на 2 ≤ 2<sup>n</sup>: 2<sup>0</sup>, 2<sup>2</sup>, 2<sup>4</sup>, 2<sup>6</sup>, …, 2<sup>n</sup>. 

```python
import math
n = int(input())
for i in range(0, n + 1, 2):
    print(pow(2, i))
```

---
# Задача 4 - Numbers N...1

Напишете програма, която чете цяло положително число n, въведено от потребителя и печата числата от n до 1 в обратен ред. Въведеното число n, винаги ще бъде по-голямо от 1.

```python
n = int(input())
for i in range(n, 0, -1):
    print(i)
```

---
# Задача 5 - Character Sequence

Напишете програма, която чете текст (стринг), въведен от потребителя и печата всеки символ от текста на отделен ред.

```python
word = input()
for i in range(0, len(word), 1):
    print(word[i])
```

---
# Задача 6 - Vowels Sum

Да се напише програма, която чете текст (стринг), въведен от потребителя, и изчислява и отпечатва сумата от стойностите на гласните букви според таблицата по-долу:

| Букви | a | e | i | o | u |
| - | - | - | - | - | - |
| Стройност | 1 | 2 | 3 | 4 | 5 |

```python
word = input()
sum = 0
for i in range(0, len(word), 1):
    if word[i] == 'a': sum += 1
    if word[i] == 'e': sum += 2
    if word[i] == 'i': sum += 3
    if word[i] == 'o': sum += 4
    if word[i] == 'u': sum += 5
print(sum)
```

---
# Задача 7 - Sum Numbers

Да се напише програма, която чете n-на брой цели числа, въведени от потребителя и ги сумира.
+	От първия ред на входа се въвежда броят числа n.
+	От следващите n реда се въвежда по едно цяло число.

Програмата трябва да прочете числата, да ги сумира и да отпечата сумата им. 


```python
n = int(input())
sum = 0
for i in range(1, n + 1, 1):
    num = int(input())
    sum += num
print(sum)
```

---
# Задача 8 - Number sequence

Напишете програма, която чете n на брой цели числа. Принтирайте най-голямото и най-малкото число сред въведените.

```python
import sys
n = int(input())
max_num = -sys.maxsize
min_num = sys.maxsize
for i in range(1, n + 1, 1):
    num = int(input())
    if num > max_num: max_num = num
    if num < min_num: min_num = num
print(f'Max number: {max_num}')
print(f'Min number: {min_num}')
```

---
# Задача 9 - Left and Right Sum

Да се напише програма, която чете 2 * n - на брой цели числа, подадени от потребителя, и проверява дали сумата на първите n числа (лява сума) е равна на сумата на вторите n числа (дясна сума). При равенство печата " Yes, sum = " + сумата; иначе печата " No, diff = " + разликата. Разликата се изчислява като положително число (по абсолютна стойност). 


```python
import math
n = int(input())
sum_right = 0
sum_left = 0
for i in range(1, n + 1, 1):
    num = int(input())
    sum_right += num
for i in range(1, n + 1, 1):
    num = int(input())
    sum_left += num
if sum_right == sum_left:
    print(f'Yes, sum = {sum_right}')
else:
    print(f'No, diff = {abs(sum_right - sum_left)}')
```

---
# Задача 10 - Odd Even Sum

Да се напише програма, която чете n-на брой цели числа, подадени от потребителя и проверява дали сумата от числата на четни позиции е равна на сумата на числата на нечетни позиции. 
+	Ако сумите са равни да се отпечатат два реда: "Yes" и на нов ред "Sum = " + сумата; 
+	Ако сумите не са равни да се отпечат два реда: "No" и на нов ред "Diff = " + разликата. 

Разликата се изчислява по абсолютна стойност. 



```python
import math
n = int(input())
sum_even = 0
sum_odd = 0
for i in range(0, n, 1):
    num = int(input())
    if i % 2 == 0:
        sum_even += num
    if i % 2 != 0:
        sum_odd += num
if sum_even == sum_odd:
    print(f'Yes')
    print(f'Sum = {sum_even}')
else:
    print(f'No')
    print(f'Diff = {abs(sum_even - sum_odd)}')
```
