# Задача 1 - Number Pyramid

Напишете програма, която чете цяло число n, въведено от потребителя, и отпечатва пирамида от числа като в примерите:

```python
n = int(input())
current = 1
is_current_bigger = False
for row in range(1, n + 1):
    for col in range(1, row + 1):
        if current > n:
            is_current_bigger = True
            break
        print(str(current) + ' ', end = '')
        current += 1
    if is_current_bigger:
        break
    print()
```

---
# Задача 2 - Equal Sums Even Odd Position

Напишете програма, която чете от конзолата две шестцифрени цели числа. Винаги първото въведено число ще бъде по-малко от второто. На конзолата да се отпечатат на 1, ред разделени с интервал, всички числа, които се намират между двете, прочетени от конзолата числа и отговарят на условието сумата от цифрите на четни и нечетни позиции да са равни. Ако няма числа, отговарящи на условието на конзолата не се извежда резултат. 

```python
start = int(input())
end = int(input())
for i in range(start, end + 1):
    i_to_str = str(i)
    sum_odd = 0
    sum_even = 0
    for index, digit in enumerate(i_to_str):
        if index % 2 == 0:
            sum_odd += int(digit)
        else:
            sum_even += int(digit)
    if sum_even == sum_odd:
        print(i, end = ' ')
```

---
# Задача 3 - Sum Prime Non Prime

Напишете програма, която чете от конзолата цели числа, докато не се получи команда "stop". Да се намери сумата на всички въведени прости и сумата на всички въведени непрости числа. Тъй като по дефиниция от математиката отрицателните числа не могат да бъдат прости, ако на входа се подаде отрицателно число, да се изведе следното съобщение "Number is negative.". В този случай въведено число се игнорира и не се прибавя към нито една от двете суми, а програмата продължава своето изпълнение, очаквайки въвеждане на следващо число. <br>
На изхода да се отпечатат на два реда двете намерени суми в следния формат:
+	"Sum of all prime numbers is: {prime numbers sum}"
+	"Sum of all non prime numbers is: {nonprime numbers sum}"


```python
number = input()
sum_prime = 0
sum_non_prime = 0
non_prime = False
while number != 'stop':
    if int(number) < 0:
        print(f'Number is negative.')
        number = input()
        continue
    for i in range(2, int(number)):
        if int(number) % i == 0:
            sum_non_prime += int(number)
            non_prime = True
            break
    if not non_prime:
        sum_prime += int(number)
    non_prime = False
    number = input()
print(f'Sum of all prime numbers is: {sum_prime}')
print(f'Sum of all non prime numbers is: {sum_non_prime}')
```

---
# Задача 4 - Train The Trainers

Курсът "Train the trainers" е към края си и финалното оценяване наближава. Вашата задача е да помогнете на журито, което ще оценява презентациите, като напишете програма, в която да изчислява средната оценка от представянето на всяка една презентация от даден студент, а накрая - средния успех от всички тях.<br>
От конзолата на първият ред се прочита броят на хората в журито n - цяло число.<br>
След това на отделен ред се прочита името на презентацията – текст.<br>
За всяка една презентация на нов ред се четат n - на брой оценки - реално число.<br>
След изчисляване на средната оценка за конкретна презентация, на конзолата се печата:<br>
 "{името на презентацията} - {средна оценка}."<br>
След получаване на команда "Finish", на конзолата се печата "Student's final assessment is {среден успех от всички презентации}." и програмата приключва.<br>
Всички оценки трябва да бъдат форматирани до втория знак след десетичната запетая.


```python
n = int(input())
total_grade = 0
grade = 0
presentation = input()
count_presentations = 0
while presentation != 'Finish':
    for i in range(1, n + 1):
        grade += float(input())
    total_grade += grade
    grade /= n
    print(f'{presentation} - {grade:.2f}.')
    grade = 0
    presentation = input()
    count_presentations += 1
print(f"Student's final assessment is {total_grade / (n * count_presentations):.2f}.")
```

---
# Задача 5 - Special Numbers

Да се напише програма, която чете едно цяло число N, въведено от потребителя, и генерира всички възможни "специални" числа от 1111 до 9999. За да бъде “специално” едно число, то трябва да отговаря на следното условие: 
+	N да се дели на всяка една от неговите цифри без остатък.

Пример: при N = 16, 2418 е специално число:
+	16 / 2 = 8 без остатък
+	16 / 4 = 4 без остатък
+	16 / 1 = 16 без остатък
+	16 / 8 = 2 без остатък


```python
n = int(input())
is_special = True
for i in range(1111, 10000):
    i_to_str = str(i)
    for index, digit in enumerate(i_to_str):
        if int(digit) == 0: is_special = False; break
        if n % int(digit) != 0: is_special = False; break
    if is_special: print(i, end = " ")
    is_special = True
```

---
# Задача 6 - Cinema Tickets

Вашата задача е да напишете програма, която да изчислява процента на билетите за всеки тип от продадените билети: студентски(student), стандартен(standard) и детски(kid), за всички прожекции. Трябва да изчислите и колко процента от залата е запълнена за всяка една прожекция.

```python
movie_name = input()
standard_tickets = 0
kid_tickets = 0
student_tickets = 0
 
while movie_name != 'Finish':
    free_places = int(input())
    current_movie_tickets = 0
    ticket_type = ""
 
    while free_places > current_movie_tickets and ticket_type != 'End':
        ticket_type = input()
 
        if ticket_type == 'standard':
            standard_tickets += 1
            current_movie_tickets += 1
        elif ticket_type == 'student':
            student_tickets += 1
            current_movie_tickets += 1
        elif ticket_type == 'kid':
            kid_tickets += 1
            current_movie_tickets += 1
 
    current_movie_percent = (current_movie_tickets / free_places) * 100
    print(f"{movie_name} - {current_movie_percent:.2f}% full.")
    movie_name = input()
 
total_tickets = student_tickets + standard_tickets + kid_tickets
 
avr_kid_percent = (kid_tickets / total_tickets) * 100
avr_student_percent = (student_tickets / total_tickets) * 100
avr_standard_percent = (standard_tickets / total_tickets) * 100
print(f'Total tickets: {total_tickets}')
print(f"{avr_student_percent:.2f}% student tickets.")
print(f"{avr_standard_percent:.2f}% standard tickets.")
print(f"{avr_kid_percent:.2f}% kids tickets.")
```
