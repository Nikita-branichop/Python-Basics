# Задача 1 - Сумиране на секунди 

Трима спортни състезатели финишират за някакъв брой секунди (между 1 и 50). Да се напише програма, която чете времената на състезателите в секунди, въведени от потребителя и пресмята сумарното им време във формат "минути:секунди". Секундите да се изведат с водеща нула (2 &rArr; "02", 7 &rArr; "07", 35 &rArr; "35"). 

```python
first = int(input())
second = int(input())
third = int(input())
time = first + second + third
minutes = time // 60
seconds = time % 60
if seconds < 10: print(f'{minutes}:0{seconds}')
else: print(f'{minutes}:{seconds}')
```

---
# Задача 2 - Бонус точки

2.	Бонус точки
Дадено е цяло число – начален брой точки. Върху него се начисляват бонус точки по правилата, описани по-долу. Да се напише програма, която пресмята бонус точките, които получава числото и общия брой точки (числото + бонуса).<br>
•	Ако числото е до 100 включително, бонус точките са 5;<br>
•	Ако числото е по-голямо от 100, бонус точките са 20% от числото;<br>
•	Ако числото е по-голямо от 1000, бонус точките са 10% от числото.<br>

•	Допълнителни бонус точки (начисляват се отделно от предходните):<br>
  +	За четно число &rArr; + 1 т.<br>
  +	За число, което завършва на 5 &rArr; + 2 т.<br>


```python
bonus = int(input())
extra_bonus = 0
if bonus <= 100: extra_bonus = 5
if 100 < bonus <= 1000: extra_bonus = bonus * 0.2
if bonus > 1000: extra_bonus = bonus * 0.1
if bonus % 2 == 0: extra_bonus  += 1
if bonus % 10 == 5: extra_bonus += 2
print(extra_bonus)
print(bonus + extra_bonus)
```

---
# Задача 3 - Време + 15 минути

Да се напише програма, която чете час и минути от 24-часово денонощие, въведени от потребителя и изчислява колко ще е часът след 15 минути. Резултатът да се отпечата във формат часове:минути. Часовете винаги са между 0 и 23, а минутите винаги са между 0 и 59. Часовете се изписват с една или две цифри. Минутите се изписват винаги с по две цифри, с водеща нула, когато е необходимо. 

```python
hours = int(input())
minutes = int(input())
if minutes + 15 > 59:
    minutes -= 45
    hours += 1
else: minutes += 15
if hours > 23:
    hours = 0
if minutes < 10: print(f'{hours}:0{minutes}')
else: print(f'{hours}:{minutes}')
```

---
# Задача 4 - Магазин за детски играчки

Петя има магазин за детски играчки. Тя получава голяма поръчка, която трябва да изпълни. С парите, които ще спечели иска да отиде на екскурзия. <br>
Цени на играчките:<br>
•	Пъзел - 2.60 лв.<br>
•	Говореща кукла - 3 лв.<br>
•	Плюшено мече - 4.10 лв.<br>
•	Миньон - 8.20 лв.<br>
•	Камионче - 2 лв.<br>
Ако поръчаните играчки са 50 или повече магазинът прави отстъпка 25% от общата цена. От спечелените пари Петя трябва да даде 10% за наема на магазина. Да се пресметне дали парите ще ѝ стигнат да отиде на екскурзия.


```python
price_journey = float(input())
puzzle = int(input())
doll = int(input())
teddy_bear = int(input())
minion = int(input())
truck = int(input())
sum = puzzle * 2.60 + doll * 3 + teddy_bear * 4.10 + minion * 8.20 + truck * 2
amount = puzzle + doll + teddy_bear + minion + truck
if amount >= 50: sum -= sum * 0.25
sum -= sum * 0.1
if sum >= price_journey: print(f'Yes! {sum - price_journey:.2f} lv left.')
else: print(f'Not enough money! {price_journey - sum:.2f} lv needed.')
```

---
# Задача 5 - Годзила срещу Конг

Снимките за дългоочаквания филм "Годзила срещу Конг" започват. Сценаристът Адам Уингард ви моли да напишете програма, която да изчисли, дали предвидените средства са достатъчни за снимането на филма. За снимките  ще бъдат нужни определен брой статисти, облекло за всеки един статист и декор.<br>
Известно е, че:<br>
•	Декорът за филма е на стойност 10% от бюджета. <br>
•	При повече от 150 статиста,  има отстъпка за облеклото на стойност 10%.


```python
budget = float(input())
extras = int(input())
price_clothes = float(input())
decoration = budget * 0.1
clothes = extras * price_clothes
if extras > 150: clothes -= clothes * 0.1
if budget >= decoration + clothes:
    print(f'Action!')
    print(f'Wingard starts filming with {budget - decoration - clothes:.2f} leva left.')
else:
    print(f'Not enough money!')
    print(f'Wingard needs {decoration + clothes - budget:.2f} leva more.')
```

---
# Задача 6 - Световен рекорд по плуване

Иван решава да подобри Световния рекорд по плуване на дълги разстояния. На конзолата се въвежда рекордът в секунди, който Иван трябва да подобри,  разстоянието в метри, което трябва да преплува и времето в секунди, за което плува разстояние от 1 м. Да се напише програма, която изчислява дали се е справил със задачата, като се има предвид, че: съпротивлението на водата го забавя на всеки 15 м. с 12.5 секунди. Когато се изчислява колко пъти Иванчо ще се забави, в резултат на съпротивлението на водата, резултатът трябва да се закръгли надолу до най-близкото цяло число.<br>
Да се изчисли времето в секунди, за което Иванчо ще преплува разстоянието и разликата спрямо Световния рекорд. 


```python
record = float(input())
distance = float(input())
time_for_metre = float(input())
total_time = distance * time_for_metre + int(distance / 15) * 12.5
if record <= total_time:
    print(f'No, he failed! He was {total_time - record:.2f} seconds slower.')
else: print(f'Yes, he succeeded! The new world record is {total_time:.2f} seconds.')
```

---
# Задача 7 - Пазаруване

Петър иска да купи N видеокарти, M процесора и P на брой рам памет. Ако броя на видеокартите е по-голям от този на процесорите получава 15% отстъпка от крайната сметка. Важат следните цени:<br>
•	Видеокарта – 250 лв./бр.<br>
•	Процесор – 35% от цената на закупените видеокарти/бр.<br>
•	Рам памет – 10% от цената на закупените видеокарти/бр.<br>
Да се изчисли нужната сума за закупуване на материалите и да се пресметне дали бюджета ще му стигне.


```python
budget = float(input())
videocard = int(input())
proccessor = int(input())
ram = int(input())
sum_videocard = videocard * 250
sum_proccessor = sum_videocard * 0.35 * proccessor
sum_ram = sum_videocard * 0.1 * ram
total_sum = sum_ram + sum_proccessor + sum_videocard
if videocard > proccessor: total_sum -= total_sum * 0.15
if budget >= total_sum:
    print(f'You have {budget - total_sum:.2f} leva left!')
else: print(f'Not enough money! You need {total_sum - budget:.2f} leva more!')
```

---
# Задача 8 - Обедна почивка

По време на обедната почивка искате да изгледате епизод от своя любим сериал. Вашата задача е да напишете програма, с която ще разберете дали имате достатъчно време да изгледате епизода. По време на почивката отделяте време за обяд и време за отдих. Времето за обяд ще бъде 1/8 от времето за почивка, а времето за отдих ще бъде 1/4 от времето за почивка. 

```python
import math
name = input()
episode_time = int(input())
break_time = int(input())
lunch = break_time / 8
break_relax = break_time / 4
if break_time - lunch - break_relax >= episode_time:
    print(f'You have enough time to watch {name} and left with {math.ceil(break_time - lunch - break_relax - episode_time)} minutes free time.')
else: print(f"You don't have enough time to watch {name}, you need {math.ceil(episode_time - break_time + lunch + break_relax)} more minutes.")
```
