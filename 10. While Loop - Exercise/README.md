# Задача 1 - Old Books

Ани отива до родния си град след много дълъг период извън страната. Прибирайки се вкъщи, тя вижда старата библиотека на баба си и си спомня за любимата си книга. Помогнете на Ани, като напишете програма, в която тя въвежда търсената от нея книга (текст). Докато Ани не намери любимата си книга или не провери всички книги в библиотеката, програмата трябва да чете всеки път на нов ред името на всяка следваща книга (текст), която тя проверява. Книгите в библиотеката са свършили щом получите текст "No More Books".
+	Ако не открие търсената книгата да се отпечата на два реда: 
    +	"The book you search is not here!"
    +	"You checked {брой} books."
+	Ако открие книгата си се отпечатва един ред:
    +	"You checked {брой} books and found it."  


```python
search_book = input()
book = input()
i = 0
while book != 'No More Books':
    if book == search_book:
        print(f'You checked {i} books and found it.'); exit(0)
    book = input()
    i += 1
print(f'The book you search is not here!')
print(f'You checked {i} books.')
```

---
# Задача 2 - Exam Preparation

Напишете програма, в която Марин решава задачи от изпити, докато не получи съобщение "Enough" от лектора си. При всяка решена задача той получава оценка. Програмата трябва да приключи прочитането на данни при команда "Enough" или ако Марин получи определения брой незадоволителни оценки. Незадоволителна е всяка оценка, която е по-малка или равна на 4.

```python
max_worse_grades = int(input())
average_score = 0.0
name_problem = input()
grade_problem = int(input())
average_score += grade_problem
i = 1
i_worse = 0
while name_problem != 'Enough':
    if grade_problem <= 4:
        i_worse += 1
        if max_worse_grades == i_worse:
            print(f'You need a break, {i_worse} poor grades.'); exit(0)
    name = name_problem
    name_problem = input()
    if name_problem == 'Enough': break
    grade_problem = int(input())
    i += 1; average_score += grade_problem
print(f'Average score: {average_score / i:.2f}')
print(f'Number of problems: {i}')
print(f'Last problem: {name}')
```

---
# Задача 3 - Vacation

Джеси е решила да събира пари за екскурзия и иска от вас да ѝ помогнете да разбере дали ще успее да събере необходимата сума. Тя спестява или харчи част от парите си всеки ден. Ако иска да похарчи повече от наличните си пари, то тя ще похарчи колкото има и ще ѝ останат 0 лева.

```python
need_money = float(input())
money_now = float(input())
all_days = 0
cant_save = 0
cant_save_bool = False
while money_now < need_money:
    do = input()
    do_money = float(input())
    if do == 'save':
        money_now += do_money
        cant_save = 0
    if do == 'spend':
        money_now -= do_money
        cant_save += 1
        if money_now < 0: money_now = 0
        if cant_save == 5: cant_save_bool = True; break
    all_days += 1
if cant_save_bool:
    print(f"You can't save the money.")
    print(f'{all_days + 1}')
else:
    print(f'You saved the money for {all_days} days.')
```

---
# Задача 4 - Walking

Габи иска да започне здравословен начин на живот и си е поставила за цел да върви 10 000 стъпки всеки ден. Някои дни обаче е много уморена от работа и ще иска да се прибере преди да постигне целта си. Напишете програма, която чете от конзолата по колко стъпки изминава тя всеки път като излиза през деня и когато постигне целта си да се изписва "Goal reached! Good job!" и колко стъпки повече е извървяла "{разликата между стъпките} steps over the goal!" <br>
Ако иска да се прибере преди това, тя ще въведе командата "Going home" и ще въведе стъпките, които е извървяла докато се прибира. След което, ако не е успяла да постигне целта си, на конзолата трябва да се изпише: "{разликата между стъпките} more steps to reach goal."


```python
import math
goal = 0
intp = input()
while intp != 'Going home':
    goal += int(intp)
    if goal >= 10000:
        print(f'Goal reached! Good job!')
        print(f'{abs(goal - 10000)} steps over the goal!')
        exit(0)
    intp = input()
intp = int(input()); goal += intp
if goal >= 10000:
    print(f'Goal reached! Good job!')
    print(f'{abs(goal - 10000)} steps over the goal!')
else:
    print(f'{abs(goal - 10000)} more steps to reach goal.')
```

---
# Задача 5 - Coins

Производителите на вендинг машини искали да направят машините си да връщат възможно най-малко монети ресто. Напишете програма, която приема сума - рестото, което трябва да се върне и изчислява с колко най-малко монети може да стане това.

```python
cash = float(input()) * 100
i = 0
while cash >= 200:
    cash -= 200; i += 1
while cash >= 100:
    cash -= 100; i += 1
while cash >= 50:
    cash -= 50; i += 1
while cash >= 20:
    cash -= 20; i += 1
while cash >= 10:
    cash -= 10; i += 1
while cash >= 5:
    cash -= 5; i += 1
while cash >= 2:
    cash -= 2; i += 1
while cash >= 1:
    cash -= 1; i += 1
print(i)
```

---
# Задача 6 - Cake

Поканени сте на 30-ти рожден ден, на който рожденикът черпи с огромна торта. Той обаче не знае колко парчета могат да си вземат гостите от нея. Вашата задача е да напишете програма, която изчислява броя на парчетата, които гостите са взели преди тя да свърши. Ще получите размерите на тортата (широчина и дължина – цели числа и след това на всеки ред, до получаване на командата "STOP" или докато не свърши тортата, броят на парчетата, които гостите вземат от нея. Всяко парче торта е с размер 1х1 см.<br>
Да се отпечата на конзолата един от следните редове:
+	"{брой парчета} pieces are left." - ако стигнете до STOP и не са свършили парчетата торта;
+	"No more cake left! You need {брой недостигащи парчета} pieces more."


```python
count_piece = int(input()) * int(input())
intp = input()
while intp != 'STOP':
    count_piece -= int(intp)
    if count_piece < 0:
        print(f'No more cake left! You need {-count_piece} pieces more.')
        exit(0)
    intp = input()
print(f'{count_piece} pieces are left.')
```

---
# Задача 7 - Moving

На осемнадесетия си рожден ден Хосе взел решение, че ще се изнесе да живее на квартира. Опаковал багажа си в кашони и намерил подходяща обява за апартамент под наем. Той започва да пренася своя багаж на части, защото не може наведнъж. Има ограничено свободно пространство в новото си жилище, където може да разположи вещите, така че мястото да бъде подходящо за живеене.<br>
Напишете програма, която изчислява свободния обем от жилището на Хосе, който остава, след като пренесе багажа си. <br>
Всеки кашон е с точни размери:  1m x 1m x 1m.


```python
capacity = int(input()) * int(input()) * int(input())
intp = input()
while intp != 'Done':
    capacity -= int(intp)
    if capacity < 0:
        print(f'No more free space! You need {-capacity} Cubic meters more.')
        exit(0)
    intp = input()
print(f'{capacity} Cubic meters left.')
```
