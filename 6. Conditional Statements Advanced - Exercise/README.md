# Задача 1 - Cinema

В една кинозала столовете са наредени в правоъгълна форма в r реда и c колони. Има три вида прожекции с билети на различни цени:
+	Premiere - премиерна прожекция, на цена 12.00 лева;
+	Normal - стандартна прожекция, на цена 7.50 лева;
+	Discount - прожекция за деца, ученици и студенти на намалена цена от 5.00 лева.

Напишете програма, която чете тип прожекция (текст), брой редове и брой колони в залата (цели числа), въведени от потребителя, и изчислява общите приходи от билети при пълна зала. Резултатът да се отпечата във формат 2 знака след десетичната точка.  

```python
screening_type = input()
rows = int(input())
columns = int(input())
sum = 0
if screening_type == 'Premiere':
    sum = rows * columns * 12
elif screening_type == 'Normal':
    sum = rows * columns * 7.50
elif screening_type == 'Discount':
    sum = rows * columns * 5.00
print(f'{sum:.2f}')
```

---
# Задача 2 - Summer Outfit

Лятото е сезон с много променливо време и Виктор има нужда от вашата помощ. Напишете програма, която спрямо времето от денонощието и градусите да препоръча на Виктор какви дрехи да облече. Вашият приятел има различни планове за всеки етап от деня, които изискват и различен външен вид - може да ги видите от таблицата.
От конзолата се четат точно два реда:
+	Градусите - цяло число;
+	Време от денонощието - текст с три възможности "Morning", "Afternoon" или "Evening".

| Време от <br> денонощието / <br> градуси| Morning | Afternoon | Evening |
| - | - | - | - |
| 10<=градуси<=18 | Outfit = Sweatshirt<br>Shoes = Sneakers | Outfit = Shirt<br>Shoes = Moccasins | Outfit = Shirt<br>Shoes = Moccasins |
| 18<градуси<=24 | Outfit = Shirt<br>Shoes = Moccasins | Outfit = T-Shirt<br>Shoes = Sandals | Outfit = Shirt<br>Shoes = Moccasins |
| градуси>=25 | Outfit = T-Shirt<br>Shoes = Sandals | Outfit = Swim Suit<br>Shoes = Barefoot | Outfit = Shirt<br>Shoes = Moccasins |

Като изход да се отпечата на конзолата на един ред: "It's {градуси} degrees, get your {облекло} and {обувки}."

```python
temperature = int(input())
time_day = input()
if time_day == 'Morning':
    if 10 <= temperature <= 18:
        shoes = 'Sneakers'; outfit = 'Sweatshirt'
    elif 18 < temperature <= 24:
        shoes = 'Moccasins'; outfit = 'Shirt'
    elif temperature >= 25:
        shoes = 'Sandals'; outfit = 'T-Shirt'
if time_day == 'Afternoon':
    if 10 <= temperature <= 18:
        shoes = 'Moccasins'; outfit = 'Shirt'
    elif 18 < temperature <= 24:
        shoes = 'Sandals'; outfit = 'T-Shirt'
    elif temperature >= 25:
        shoes = 'Barefoot'; outfit = 'Swim Suit'
if time_day == 'Evening':
    if 10 <= temperature <= 18:
        shoes = 'Moccasins'; outfit = 'Shirt'
    elif 18 < temperature <= 24:
        shoes = 'Moccasins'; outfit = 'Shirt'
    elif temperature >= 25:
        shoes = 'Moccasins'; outfit = 'Shirt'
print(f"It's {temperature} degrees, get your {outfit} and {shoes}.")
```

---
# Задача 3 - New House

Марин и Нели си купуват къща недалеч от София. Нели толкова много обича цветята, че Ви убеждава да напишете програма, която да изчисли колко  ще им струва, за да засадят определен брой цветя и дали наличният бюджет ще им е достатъчен. Различните цветя са с различни цени:

| Цвете | Роза | Далия | Лале | Нарцис | Гладиола |
| - | - | - | - | - | - |
| Цена на брой в лева | 5 | 3.80 | 2.80 | 3 | 2.50 |

Съществуват следните отстъпки:
+	Ако Нели купи повече от 80 Рози - 10% отстъпка от крайната цена;
+	Ако Нели купи повече от 90  Далии - 15% отстъпка от крайната цена;
+	Ако Нели купи повече от 80 Лалета - 15% отстъпка от крайната цена;
+	Ако Нели купи по-малко от 120 Нарциса - цената се оскъпява с 15%;
+	Ако Нели Купи по-малко от 80 Гладиоли - цената се оскъпява с 20%.

От конзолата се четат 3 реда:
+	Вид цветя - текст с възможности "Roses", "Dahlias", "Tulips", "Narcissus" или "Gladiolus";
+	Брой цветя - цяло число;
+	Бюджет - цяло число.

Да се отпечата на конзолата на един ред:
+	Ако бюджетът им е достатъчен - "Hey, you have a great garden with {броя цвета} {вид цветя} and {останалата сума} leva left.";
+	Ако бюджета им е НЕ достатъчен - "Not enough money, you need {нужната сума} leva more.".

Сумата да бъде форматирана до втория знак след десетичната запетая.


```python
flowers = input()
amount = int(input())
budget = int(input())
sum = 0;
if flowers == 'Roses':
    if amount > 80:
        sum = amount * 5 - amount * 5 * 0.1
    else: sum = amount * 5
if flowers == 'Dahlias':
    if amount > 90:
        sum = amount * 3.80 - amount * 3.80 * 0.15
    else: sum = amount * 3.80
if flowers == 'Tulips':
    if amount > 80:
        sum = amount * 2.80 - amount * 2.80 * 0.15
    else: sum = amount * 2.80
if flowers == 'Narcissus':
    if amount < 120:
        sum = amount * 3 + amount * 3 * 0.15
    else: sum = amount * 3
if flowers == 'Gladiolus':
    if amount < 80:
        sum = amount * 2.50 + amount * 2.50 * 0.2
    else: sum = amount * 2.50
if budget >= sum:
    print(f'Hey, you have a great garden with {amount} {flowers} and {budget - sum:.2f} leva left.')
else: print(f'Not enough money, you need {sum - budget:.2f} leva more.')
```

---
# Задача 4 - Fishing Boat

Тони и приятели много обичат да ходят за риба и са толкова запалени по риболова, че решават да отидат на риболов с кораб. Цената за наема на кораба зависи от сезона и броя рибари:
В зависимост от сезона:
+	Цената за наем на кораба през пролетта е  3000 лв.;
+	Цената за наем на кораба през лятото и есента е  4200 лв.;
+	Цената за наем на кораба през зимата е  2600 лв.

В зависимост от броя на групата има различна отстъпка:
+	Ако групата е до 6 човека включително  -  отстъпка от 10%;
+	Ако групата е от 7 до 11 човека включително  -  отстъпка от 15%;
+	Ако групата е от 12 нагоре  -  отстъпка от 25%.
Рибарите ползват допълнително 5% отстъпка, ако са четен брой, освен ако не е есен - тогава нямат допълнителна отстъпка, която се начислява след като се приспадне отстъпката по горните критерии.
Напишете програма, която да пресмята дали рибарите ще съберат достатъчно пари. 



```python
budget = int(input())
season = input()
fishman = int(input())
sum = 0
if season == 'Spring':
    sum = 3000
    if fishman < 7: sum -= 3000 * 0.1
    if 6 < fishman < 12: sum -= 3000 * 0.15
    if fishman > 11: sum -= 3000 * 0.25
if season == 'Summer' or season == 'Autumn':
    sum = 4200
    if fishman < 7: sum -= 4200 * 0.1
    if 6 < fishman < 12: sum -= 4200 * 0.15
    if fishman > 11: sum -= 4200 * 0.25
if season == 'Winter':
    sum = 2600
    if fishman < 7: sum -= 2600 * 0.1
    if 6 < fishman < 12: sum -= 2600 * 0.15
    if fishman > 11: sum -= 2600 * 0.25
if fishman % 2 == 0 and season != 'Autumn':  sum = sum - (sum * 0.05)
if budget >= sum:
    print(f'Yes! You have {budget - sum:.2f} leva left.')
else: print(f'Not enough money! You need {sum - budget:.2f} leva.')
```

---
# Задача 5 - Journey

Млад програмист разполага с определен бюджет и свободно време в даден сезон. Напишете програма, която да приема на входа бюджета и сезона, а на изхода да изкарва къде ще почива програмистът и колко ще похарчи.
Бюджетът определя дестинацията, а сезонът - колко от бюджета ще изхарчи. Ако е лято ще почива на къмпинг, а зимата в хотел. Ако е в Европа, независимо от сезона, ще почива в хотел. Всеки къмпинг или хотел, според дестинацията, има собствена цена, която отговаря на даден процент от бюджета: 
+	При 100 лв. или по-малко - някъде в България:
    +	Лято - 30% от бюджета;
    +	Зима - 70% от бюджета.
+	При 1000 лв. или по малко - някъде на Балканите:
    +	Лято - 40% от бюджета;
    +	Зима - 80% от бюджета.
+	При повече от 1000 лв. - някъде из Европа:
    +	При пътуване из Европа, независимо от сезона, ще похарчи 90% от бюджета.


```python
budget = float(input())
season = input()
destination = ''
relax = ''
sum = 0
if budget <= 100:
    destination = 'Bulgaria'
    if season == 'summer': sum = budget * 0.3; relax = 'Camp'
    if season == 'winter': sum = budget * 0.7; relax = 'Hotel'
if 100 < budget <= 1000:
    destination = 'Balkans'
    if season == 'summer': sum = budget * 0.4; relax = 'Camp'
    if season == 'winter': sum = budget * 0.8; relax = 'Hotel'
if budget > 1000:
    destination = 'Europe'
    sum = budget * 0.9; relax = 'Hotel'
print(f'Somewhere in {destination}')
print(f'{relax} - {sum:.2f}')
```

---
# Задача 6 - Operations Between Numbers

Напишете програма, която чете две цели числа (N1 и N2) и оператор, с който да се извърши дадена математическа операция. Възможните операции са: Събиране(+), Изваждане(-), Умножение(*),  Деление(/) и Модулно деление(%). При събиране, изваждане и умножение на конзолата трябва да се отпечатат резултата и дали той е четен или нечетен. При обикновеното деление - резултата. При модулното деление - остатъка. Трябва да се има предвид, че делителят може да е равен на 0 (нула), а на нула не се дели. В този случай трябва да се отпечата специално съобщениe.

```python
n1 = int(input())
n2 = int(input())
operation = input()
if operation == '+':
    if (n1 + n2) % 2 == 0: print(f'{n1} + {n2} = {n1 + n2} - even')
    else: print(f'{n1} + {n2} = {n1 + n2} - odd')
if operation == '*':
    if (n1 * n2) % 2 == 0: print(f'{n1} * {n2} = {n1 * n2} - even')
    else: print(f'{n1} * {n2} = {n1 * n2} - odd')
if operation == '-':
    if (n1 - n2) % 2 == 0: print(f'{n1} - {n2} = {n1 - n2} - even')
    else: print(f'{n1} - {n2} = {n1 - n2} - odd')
if operation == '%':
    if n2 == 0: print(f'Cannot divide {n1} by zero')
    else: print(f'{n1} % {n2} = {n1 % n2}')
if operation == '/':
    if n2 == 0: print(f'Cannot divide {n1} by zero')
    else: print(f'{n1} / {n2} = {n1 / n2:.2f}')
```

---
# Задача 7 - Hotel Room

Хотел предлага 2 вида стаи: студио и апартамент. Напишете програма, която изчислява цената за целия престой за студио и апартамент. Цените зависят от месеца на престоя:

| Май и октомври | Юни и септември | Юли и август |
| - | - | - |
| Студио - 50 лв./нощувка | Студио - 75.20 лв./нощувка | Студио - 76 лв./нощувка |
| Апартамент - 65 лв./нощувка | Апартамент - 68.70 лв./нощувка | Апартамент - 77 лв./нощувка |

Предлагат се и следните отстъпки:
+	За студио, при повече от 7 нощувки през май и октомври : 5% намаление.
+	За студио, при повече от 14 нощувки през май и октомври : 30% намаление.
+	За студио, при повече от 14 нощувки през юни и септември: 20% намаление.
+	За апартамент, при повече от 14 нощувки, без значение от месеца : 10% намаление.


```python
month = input()
overnight_stays = int(input())
price_apartment = 0
price_studio = 0
if month == 'May' or month == 'October':
    price_studio = 50 * overnight_stays
    price_apartment = 65 * overnight_stays
    if 7 < overnight_stays < 15: price_studio -= price_studio * 0.05
    if 14 < overnight_stays: price_studio -= price_studio * 0.3
if month == 'June' or month == 'September':
    price_studio = 75.20 * overnight_stays
    price_apartment = 68.70 * overnight_stays
    if 14 < overnight_stays: price_studio -= price_studio * 0.2
if month == 'July' or month == 'August':
    price_studio = 76 * overnight_stays
    price_apartment = 77 * overnight_stays
if 14 < overnight_stays: price_apartment -= price_apartment * 0.1
print(f'Apartment: {price_apartment:.2f} lv.')
print(f'Studio: {price_studio:.2f} lv.')
```

---
# Задача 8 - On Time for the Exam

Студент трябва да отиде на изпит в определен час (например в 9:30 часа). Той идва в изпитната зала в даден час на пристигане (например 9:40). Счита се, че студентът е дошъл навреме, ако е пристигнал в часа на изпита или до половин час преди това. Ако е пристигнал по-рано повече от 30 минути, той е подранил. Ако е дошъл след часа на изпита, той е закъснял. Напишете програма, която прочита време на изпит и време на пристигане и отпечатва дали студентът е дошъл навреме, дали е подранил или е закъснял и с колко часа или минути е подранил или закъснял.

```python
exam_hour = int(input())
exam_minute = int(input())
arrive_hour = int(input())
arrive_minute = int(input())

exam_total_minutes = exam_hour * 60 + exam_minute
arrive_total_minutes = arrive_hour * 60 + arrive_minute

if arrive_total_minutes > exam_total_minutes:
    print("Late")
elif exam_total_minutes - arrive_total_minutes <= 30:
    print("On time")
else:
    print("Early")

result = abs(exam_total_minutes - arrive_total_minutes)
if exam_total_minutes - arrive_total_minutes > 0:
    if result < 60:
        print(f"{result} minutes before the start")
    else:
        print(f"{result // 60}:{result % 60:02d} hours before the start")
elif arrive_total_minutes - exam_total_minutes > 0:
    if result < 60:
        print(f"{result} minutes after the start")
    else:
        print(f"{result // 60}:{result % 60:02d} hours after the start")
```

---
# Задача 9 - Ski Trip

Атанас решава да прекара отпуската си в Банско и да кара ски. Преди да отиде обаче, трябва да резервира хотел и да изчисли колко ще му струва престоя. Налични са следните видове помещения, със следните цени за престой:
+ "room for one person" – 18.00 лв за нощувка
+ "apartment" – 25.00 лв за нощувка 
+ "president apartment" – 35.00 лв за нощувка

Според броят на дните, в които ще остане в хотела (пример: 11 дни = 10 нощувки) и видът на помещението, което ще избере, той може да ползва различно намаление. 
Намаленията са както следва:

| вид помещение | по-малко от 10 дни | между 10 и 15 дни | повече от 15 дни |
| - | - | - | - |
| room for one person | не ползва намаление | не ползва намаление | не ползва намаление |
| apartment | 30% от крайната цена | 35% от крайната цена | 50% от крайната цена |
| president apartment | 10% от крайната цена | 15% от крайната цена | 20% от крайната цена |

След престоя, оценката на Атанас за услугите на хотела може да е позитивна (positive) или негативна (negative) . Ако оценката му е позитивна, към цената с вече приспаднатото намаление Атанас добавя 25% от нея. Ако оценката му е негативна приспада от цената 10%.

```python
days = int(input())
room = input()
grade = input()
total_sum = 0
if room == 'room for one person':
    total_sum = (days - 1) * 18
if room == 'apartment':
    apart_sum = (days - 1) * 25
    if days < 10:
        total_sum = apart_sum - apart_sum * 0.3
    elif 10 <= days <= 15:
        total_sum = apart_sum - apart_sum * 0.35
    elif days > 15:
        total_sum = apart_sum - apart_sum * 0.5
if room == 'president apartment':
    apart_sum = (days - 1) * 35
    if days < 10:
        total_sum = apart_sum - apart_sum * 0.1
    elif 10 <= days <= 15:
        total_sum = apart_sum - apart_sum * 0.15
    elif days > 15:
        total_sum = apart_sum - apart_sum * 0.20
if grade == 'positive':
    total_sum += total_sum * 0.25
else : total_sum -= total_sum * 0.1
print(f'{total_sum:.2f}')
```
