# Задача 1 - Day of Week

Напишете програма, която чете цяло число, въведено от потребителя, и отпечатва ден от седмицата (на английски език), в граници [1...7] или отпечатва "Error" в случай, че въведеното число е невалидно. 

```python
day = int(input())
if day == 1: print('Monday')
elif day == 2: print('Tuesday')
elif day == 3: print('Wednesday')
elif day == 4: print('Thursday')
elif day == 5: print('Friday')
elif day == 6: print('Saturday')
elif day == 7: print('Sunday')
else: print('Error')
```

---
# Задача 2 - weekend or Working Day

Напишете програма която, чете ден от седмицата (текст), на английски език - въведен от потребителя.Ако денят е работен отпечатва на конзолата - "Working day", ако е почивен - "Weekend". Ако се въведе текст различен от ден от седмицата да се отпечата - "Error".

```python
day = input()
if day == 'Monday' or day == 'Tuesday' or day == 'Wednesday' or day == 'Thursday' or day == 'Friday': 
    print('Working day')
elif day == 'Sunday' or day == 'Saturday':
    print('Weekend')
else: print('Error')
```

---
# Задача 3 - Animal Type

Напишете програма, която отпечатва класа на животното според неговото име, въведено от потребителя.
+	dog -> mammal
+	crocodile, tortoise, snake -> reptile
+	others -> unknown

```python
animal = input()
if animal == 'dog': print('mammal')
elif animal == 'crocodile' or animal == 'tortoise' or animal == 'snake':
    print('reptile')
else: print('unknown')
```

---
# Задача 4 - Personal Titles

Да се напише конзолна програма, която прочита възраст (реално число) и пол ('m' или 'f'), въведени от потребителя, и отпечатва обръщение измежду следните:
+	"Mr." – мъж (пол 'm') на 16 или повече години
+	"Master" – момче (пол 'm') под 16 години
+	"Ms." – жена (пол 'f') на 16 или повече години
+	"Miss" – момиче (пол 'f') под 16 години


```python
age = float(input())
sex = input()
if sex == 'm':
    if age < 16: print('Master')
    else: print('Mr.')
if sex == 'f':
    if age < 16: print('Miss')
    else: print('Ms.')
```

---
# Задача 5 - Small Shop

Предприемчив българин отваря квартални магазинчета в няколко града и продава на различни цени според града:


| Град/Продукт | coffee | water | beer | sweets | peanuts |
| - | - | - | - | - | - |
| Sofia | 0.50 | 0.80 | 1.20 | 1.45 | 1.60 |
| Plovdiv | 0.40 | 0.70 | 1.15 | 1.30 | 1.50 |
| Varna | 0.45 | 0.70 | 1.10 | 1.35 | 1.55 |

Напишете програма, която чете продукт (текст), град (текст) и количество (десетично число), въведени от потребителя, и пресмята и отпечатва колко струва съответното количество от избрания продукт в посочения град. 


```python
product = input()
city = input()
amount = float(input())
total_price = 0
if city == 'Sofia':
    if product == 'coffee':
        total_price = 0.50
    if product == 'water':
        total_price = 0.80
    if product == 'beer':
        total_price = 1.20
    if product == 'sweets':
        total_price = 1.45
    if product == 'peanuts':
        total_price = 1.60
if city == 'Plovdiv':
    if product == 'coffee':
        total_price = 0.40
    if product == 'water':
        total_price = 0.70
    if product == 'beer':
        total_price = 1.15
    if product == 'sweets':
        total_price = 1.30
    if product == 'peanuts':
        total_price = 1.50
if city == 'Varna':
    if product == 'coffee':
        total_price = 0.45
    if product == 'water':
        total_price = 0.70
    if product == 'beer':
        total_price = 1.10
    if product == 'sweets':
        total_price = 1.35
    if product == 'peanuts':
        total_price = 1.55
print(total_price * amount)
```

---
# Задача 6 - Number in Range

Да се напише програма, която проверява дали въведеното от потребителя число е в интервала [-100, 100] и е различно от 0 и извежда "Yes", ако отговаря на условията, или "No" ако е извън тях.

```python
number = float(input())
if number < -100 or number > 100 or number == 0: print('No')
else: print('Yes')
```

---
# Задача 7 - Working Hours

Да се напише програма, която чете час от денонощието(цяло число) и ден от седмицата(текст) - въведени от потребителя и проверява дали офисът на фирма е отворен, като работното време на офисът е от 10-18 часа, от понеделник до събота включително.

```python
clock = int(input())
day = input()
if clock < 10 or clock > 18 or day == 'Sunday': print('closed')
else: print('open')
```

---
# Задача 8 - Cinema Ticket

Да се напише програма която чете ден от седмицата (текст) – въведен от потребителя и принтира на конзолата цената на билет за кино според деня от седмицата:

| Monday | Tuesday | Wednesday | Thursday | Friday | Saturday | Sunday |
| - | - | - | - | - | - | - |
| 12 | 12 | 14 | 14 | 12 | 16 | 16 |

```python
day = input()
if day == 'Wednesday' or day == 'Thursday': print(14)
elif day == 'Saturday' or day == 'Sunday': print(16)
else: print(12)
```

---
# Задача 9 - Fruit or Vegetable

Да се напише програма, която чете име на продукт, въведено от потребителя, и проверява дали е плод или зеленчук.
+	Плодовете "fruit" имат следните възможни стойности:  banana, apple, kiwi, cherry, lemon и grapes;
+	Зеленчуците "vegetable" имат следните възможни стойности:  tomato, cucumber, pepper и carrot;
+	Всички останали са "unknown".
Да се изведе "fruit", "vegetable" или "unknown" според въведения продукт.

```python
product = input()
if product == 'banana' or product == 'apple' or product == 'kiwi' or product == 'cherry' or product == 'lemon' or product == 'grapes':
    print('fruit')
elif product == 'tomato' or product == 'cucumber' or product == 'pepper' or product == 'carrot':
    print('vegetable')
else: print('unknown')
```

# Задача 10 - Invalid Number

Дадено число е валидно, ако е в диапазона [100…200] или е 0. Да се напише програма, която чете цяло число, въведено от потребителя, и печата "invalid" ако въведеното число не е валидно. 

```python
num = int(input())
if num == 0 or (num >= 100 and num <= 200): print()
else: print('invalid')
```

# Задача 11 - Fruit Shop

Магазин за плодове през работните дни работи на следните цени:

| Плод | banana | apple | orange | grapefruit | kiwi | pineapple | grapes |
| - | - | - | - | - | - | - | - |
| Цена | 2.50 | 1.20 | 0.85 | 1.45 | 2.70 | 5.50 | 3.85 |

През събота и неделя магазинът работи на по-високи цени:

| Плод | banana | apple | orange | grapefruit | kiwi | pineapple | grapes |
| - | - | - | - | - | - | - | - |
| Цена | 2.70 | 1.25 | 0.90 | 1.60 | 3.00 | 5.60 | 4.20 |

Напишете програма, която чете от конзолата следните три променливи, въведени от потребителя, и пресмята цената според цените от таблиците по-горе:
+	плод  - banana / apple / orange / grapefruit / kiwi / pineapple / grapes;
+	ден от седмицата  - Monday / Tuesday / Wednesday / Thursday / Friday / Saturday / Sunday;
+	количество (реално число).
Резултатът да се отпечата закръглен с 2 цифри след десетичната точка. При невалиден ден от седмицата или невалидно име на плод да се отпечата "error".


```python
product = input()
day = input()
amount = float(input())
price = 0
if day == 'Monday' or day == 'Tuesday' or day == 'Wednesday' or day == 'Thursday' or day == 'Friday':
    if product == 'banana': price = 2.50
    elif product == 'apple': price = 1.20
    elif product == 'orange': price = 0.85
    elif product == 'grapefruit': price = 1.45
    elif product == 'kiwi': price = 2.70
    elif product == 'pineapple': price = 5.50
    elif product == 'grapes': price = 3.85
    else: print('error'), exit(0)
    print(f'{price * amount:.2f}')
elif day == 'Saturday' or day == 'Sunday':
    if product == 'banana': price = 2.70
    elif product == 'apple': price = 1.25
    elif product == 'orange': price = 0.90
    elif product == 'grapefruit': price = 1.60
    elif product == 'kiwi': price = 3.00
    elif product == 'pineapple': price = 5.60
    elif product == 'grapes': price = 4.20
    else: print('error'), exit(0)
    print(f'{price * amount:.2f}')
else: print('error')
```

# Задача 12 - Trade Commissions

Фирма дава следните комисионни на търговците си според града, в който работят и обема на продажбите:

| Град | 0 &le; s &le; 500 | 500 &lt; s &le; 1 000 | 1 000 &lt; s &le; 10 000 | s &gt; 10 000 |
| - | - | - | - | - |
| Sofia | 5% | 7% | 8% | 12% |
| Varna | 4.5% | 7.5% | 10% | 13% |
| Plovdiv | 5.5% | 8% | 12% | 14.5% |

Напишете конзолна програма, която чете име на град (текст) и обем на продажби (реално число), въведени от потребителя, и изчислява и извежда размера на търговската комисионна според горната таблица. Резултатът да се изведе форматиран до 2 цифри след десетичната точка. При невалиден град или обем на продажбите (отрицателно число) да се отпечата "error". 

```python
city = input()
sales = float(input())
precent = 0
if 0 <= sales <= 500:
    if city == 'Sofia': precent = 5
    elif city == 'Varna': precent = 4.5
    elif city == 'Plovdiv': precent = 5.5
    else: print('error'), exit(0)
elif 500 < sales <= 1000:
    if city == 'Sofia': precent = 7
    elif city == 'Varna': precent = 7.5
    elif city == 'Plovdiv': precent = 8
    else: print('error'), exit(0)
elif 1000 < sales <= 10000:
    if city == 'Sofia': precent = 8
    elif city == 'Varna': precent = 10
    elif city == 'Plovdiv': precent = 12
    else: print('error'), exit(0)
elif sales > 10000:
    if city == 'Sofia': precent = 12
    elif city == 'Varna': precent = 13
    elif city == 'Plovdiv': precent = 14.5
    else: print('error'), exit(0)
else: print('error'), exit(0)
print(f'{sales * precent / 100:.2f}')
```
