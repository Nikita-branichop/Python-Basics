# Задача 1 - Numbers Ending in 7

Напишете програма, която отпечатва числата в диапазона от 1 до 1000, които завършват на 7.

```python
for i in range(0, 1001, 1):
    if i % 10 == 7:
        print(i)
```

---
# Задача 2 - Half Sum Element

Да се напише програма, която чете n-на брой цели числа, въведени от потребителя,и проверява дали сред тях съществува число, което е равно на сумата на всички останали. 
+	Ако има такъв елемент печата "Yes" и на нов ред "Sum = "  + неговата стойност
+	Ако няма такъв елемент печата "No" и на нов ред "Diff = " + разликата между най-големия елемент и сумата на останалите (по абсолютна стойност)


```python
import sys
import math
n = int(input())
max_num = -sys.maxsize
sum_num = 0
for i in range(0, n):
    num = int(input())
    if num > max_num: max_num = num
    sum_num += num
if sum_num - max_num == max_num:
    print(f'Yes')
    print(f'Sum = {max_num}')
else:
    print(f'No')
    print(f'Diff = {abs(2 * max_num - sum_num)}')
```

---
# Задача 3 - Histogram

Дадени са n цели числа в интервала [1…1000]. От тях някакъв процент p1 са под 200, друг процент p2 са от 200 до 399, друг процент p3 са от 400 до 599, друг процент p4 са от 600 до 799 и останалите p5 процента са от 800 нагоре. Да се напише програма, която изчислява и отпечатва процентите p1, p2, p3, p4 и p5.

```python
n = int(input())
p1 = 0; p2 = 0; p3 = 0; p4 = 0; p5 = 0
for i in range(0, n):
    num = int(input())
    if num < 200: p1 += 1
    if 200 <= num < 400: p2 += 1
    if 400 <= num < 600: p3 += 1
    if 600 <= num < 800: p4 += 1
    if num >= 800: p5 += 1
print(f'{p1 / n * 100:.2f}%')
print(f'{p2 / n * 100:.2f}%')
print(f'{p3 / n * 100:.2f}%')
print(f'{p4 / n * 100:.2f}%')
print(f'{p5 / n * 100:.2f}%')
```

---
# Задача 4 - Clever Lily

Лили вече е на N години. За всеки свой рожден ден тя получава подарък. 
+	За нечетните рождени дни (1, 3, 5...n) получава играчки.
+	За четните рождени дни (2, 4, 6...n) получава пари. 

За втория рожден ден получава 10.00 лв, като сумата се увеличава с 10.00 лв., за всеки следващ четен рожден ден (2 -> 10, 4 -> 20, 6 -> 30...и т.н.). През годините Лили тайно е спестявала парите. Братът на Лили, в годините, които тя получава пари, взима по 1.00 лев от тях. Лили продала играчките получени през годините, всяка за P лева и добавила сумата към спестените пари. С парите искала да си купи пералня за X лева. Напишете програма, която да пресмята, колко пари е събрала и дали ѝ стигат да си купи пералня.


```python
ages = int(input())
price_tech = float(input())
price_toy = int(input())
money = 10
total_sum = -(ages // 2)
for i in range(1, ages + 1):
    if i % 2 == 0:
        total_sum += money
        money += 10
    if i % 2 != 0:
        total_sum += price_toy
if price_tech <= total_sum:
    print(f'Yes! {total_sum - price_tech:.2f}')
else:
    print(f'No! {price_tech - total_sum:.2f}')
```

---
# Задача 5 - Salary

Шеф на компания забелязва че все повече служители прекарват  време в сайтове, които ги разсейват.  
За да предотврати това, той въвежда изненадващи проверки на отворените табове на браузъра на служителите си. <br>
Според отворения сайт в таба се налагат следните глоби:
+	"Facebook" -> 150 лв.
+	"Instagram" -> 100 лв.
+	"Reddit" -> 50 лв.

От конзолата се четат два реда:
+	Брой отворени табове в браузъра n - цяло число в интервала [1...10]
+	Заплата - число в интервала [500...1500]

След това n – на брой пъти се чете име на уебсайт – текст


```python
tabs = int(input())
salary = int(input())
for i in range(0, tabs):
    site = input()
    if site == 'Facebook': salary -= 150
    if site == 'Instagram' : salary -= 100
    if site == 'Reddit': salary -= 50
if salary > 0:
    print(salary)
else:
    print(f'You have lost your salary.')
```

---
# Задача 6 - Oscars

Поканени сте от академията да напишете софтуер, който да пресмята точките за актьор/актриса. Академията ще ви даде първоначални точки за актьора. След това всеки оценяващ ще дава своята оценка. Точките, които актьора получава се формират от: дължината на името на оценяващия умножено по точките, които дава делено на две. <br>
Ако резултатът в някой момент надхвърли 1250.5 програмата трябва да прекъсне и да се отпечата, че дадения актьор е получил номинация.


```python
name_actor = input()
total_points = float(input())
count_judges = int(input())
for i in range(0, count_judges):
    name_judge = input()
    points_judge = float(input())
    total_points += (len(name_judge) * points_judge / 2)
    if total_points >= 1250.5:
        print(f'Congratulations, {name_actor} got a nominee for leading role with {total_points:.1f}!'); exit(0)
print(f'Sorry, {name_actor} you need {1250.5 - total_points:.1f} more!')
```

---
# Задача 7 - Trekking Mania

Катерачи от цяла България се събират на групи и набелязват следващите върхове за изкачване. Според размера на групата, катерачите ще изкачват различни върхове.
+	Група до 5 човека – изкачват Мусала
+	Група от 6 до 12 човека – изкачват Монблан
+	Група от 13 до 25 човека – изкачват Килиманджаро
+	Група от 26 до 40 човека –  изкачват К2
+	Група от 41 или повече човека – изкачват Еверест

Да се напише програма, която изчислява процента на катерачите изкачващи всеки връх.



```python
groups = int(input())
all_people = 0
musala = 0; monblan = 0; kilimon = 0; k2 = 0; everest = 0
for i in range(0, groups):
    people_group = int(input())
    if people_group <= 5: musala += people_group
    if 6 <= people_group <= 12: monblan += people_group
    if 13 <= people_group <= 25: kilimon += people_group
    if 26 <= people_group <= 40: k2 += people_group
    if people_group >= 41: everest += people_group
    all_people += people_group
print(f'{musala / all_people * 100:.2f}%')
print(f'{monblan / all_people * 100:.2f}%')
print(f'{kilimon / all_people * 100:.2f}%')
print(f'{k2 / all_people * 100:.2f}%')
print(f'{everest / all_people * 100:.2f}%')
```

---
# Задача 8 - Tennis Ranklist

Григор Димитров е тенисист, чиято следваща цел е изкачването в световната ранглиста по тенис за мъже. <br> 
През годината Гришо участва в определен брой турнири, като за всеки турнир получава точки, които зависят от позицията, на която е завършил в турнира. Има три варианта за завършване на турнир:
+	W - ако е победител получава 2000 точки
+	F - ако е финалист получава 1200 точки
+	SF - ако е полуфиналист получава 720 точки

Напишете програма, която изчислява колко ще са точките на Григор след изиграване на всички турнири, като знаете с колко точки стартира сезона. Също изчислете колко точки средно печели от всички изиграни турнири и колко процента от турнирите е спечелил. 


```python
import math
count_tour = int(input())
begin_points = int(input())
later_points = 0
wins = 0
for i in range(0, count_tour):
    stage = input()
    if stage == 'W': later_points += 2000; wins += 1
    if stage == 'F': later_points += 1200
    if stage == 'SF': later_points += 720
print(f'Final points: {begin_points + later_points}')
print(f'Average points: {math.floor(later_points / count_tour)}')
print(f'{wins / count_tour * 100:.2f}%')
```
