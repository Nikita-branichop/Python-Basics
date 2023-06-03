# Задача 1 - Series Calculator

Напишете програма, която изчислява колко време ще ви отнеме да изгледате всички епизоди на 
един сериал в минути. Ще разполагате с брой сезони, брой епизоди на сезон и времетраене на 
един епизод. Във всеки епизод има реклами, които са с продължителност 20% от времето на 
един епизод. Също така знаете, че всеки сезон завършва със специален епизод, който е с 10м по-дълъг от обичайното. 

```python
serial = input()
season = int(input())
episodes = int(input())
episode_without_adv = float(input())
all_time = (episode_without_adv + (episode_without_adv * 0.2)) * episodes * season + (season * 10)
print(f'Total time needed to watch the {serial} series is {int(all_time)} minutes.')
```

---
# Задача 2 - Skeleton

Българският състезател по скелетон Марин Бангиев се бори за олимпийска квота. Вие имате честта 
да напишете програмата, която ще изчисли дали той печели квота. <br>
Вашата програма получава контролата в минути, която трябва да бъде достигната или подобрена,
за да може Марин да вземе квота. Също така програмата ще получи разстоянието на улея в 
метри, и времето в секунди, за което той изминава 100 метра.<br>
Трябва да се има предвид, че поради наклона на улея, на всеки 120 метра неговото време намаля 
с 2.5 секунди.

```python
Minutes = int(input())
Seconds = int(input())
Distance = float(input())
Seconds_100m = int(input())
finish_time = Minutes * 60 + Seconds
his_time = (Distance / 100) * Seconds_100m - (Distance / 120 * 2.5)
if his_time <= finish_time:
    print(f'Marin Bangiev won an Olympic quota!')
    print(f'His time is {his_time:.3f}.')
else:
    print(f'No, Marin failed! He was {his_time - finish_time:.3f} second slower.')
```

---
# Задача 3 - Painting Eggs

С наближаването на Великденските празници, цех за боядисване на яйца, започва да боядисва 
различни размери яйца, които след това продава на партиди. В таблицата са показани размерите 
на яйцата, различните бои и каква е цената за продажба на една партида яйца, зависеща от 
размерите и цвета боя. 

|  | Червено (Red) | Зелено (Green) | Жълто (Yellow) |
| - | - | - | - |
| Големи (Large) | 16 лв. | 12 лв. | 9 лв. |
| Средни (Medium) | 13 лв. | 9 лв. | 7 лв. |
| Малки (Small) | 16 лв. | 12 лв. | 5 лв. |

Напишете програма, която изчислява какви ще са приходите на цеха от продажбите, като знаете 
размера на яйцата и техният цвят. С 35% от крайната цена ще бъдат покрити производствени 
разходи.

```python
Size = input()
Color = input()
Count = int(input())
total = 0
if Size == 'Large':
    if Color == 'Red': total = 16
    if Color == 'Green': total = 12
    if Color == 'Yellow': total = 9
if Size == 'Medium':
    if Color == 'Red': total = 13
    if Color == 'Green': total = 9
    if Color == 'Yellow': total = 7
if Size == 'Small':
    if Color == 'Red': total = 9
    if Color == 'Green': total = 8
    if Color == 'Yellow': total = 5
total = (total * Count) - (total * Count * 0.35)
print(f'{total:.2f} leva.')
```

---
# Задача 4 - Balls

В кутия имаме неопределен брой топки с различни цветове, които ни носят различен брой точки. 
Задачата ни е да извадим Х бр. топки, които ще бъдат въведени от конзолата, като се има в 
предвид, че всеки различен цвят влияе на точките ни по следния начин:
+ Ако топката е "red" точките ни се повишават с 5.
+ Ако топката е "orange" точките ни се повишават с 10.
+ Ако топката е "yellow" точките ни се повишават с 15.
+ Ако топката е "white" точките ни се повишават с 20.
+ Ако топката е "black" точките ни се делят на 2 (целочислено).

Ако топката е с какъвто и да е цвят, различен от по-горните, точките не се манипулират и 
програмата продължава да работи.

```python
n = int(input())
points = 0
red = 0
orange = 0
yellow = 0
white = 0
other = 0
divides = 0
for i in range (0, n):
    ball = input()
    if ball == 'red': points += 5; red += 1
    elif ball == 'orange': points += 10; orange += 1
    elif ball == 'yellow': points += 15; yellow += 1
    elif ball == 'white': points += 20; white += 1
    elif ball == 'black': points //= 2; divides += 1
    else: other += 1
print(f'Total points: {points}')
print(f'Red balls: {red}')
print(f'Orange balls: {orange}')
print(f'Yellow balls: {yellow}')
print(f'White balls: {white}')
print(f'Other colors picked: {other}')
print(f'Divides from black balls: {divides}')
```

---
# Задача 5 - Care of Puppy

Ани намира кученце, за което ще се грижи, докато се намери някой да го осинови. То изяжда 
дневно определено количество храна. Да се напише програма, която проверява дали 
количеството храна, което е закупено за кученцето, ще е достатъчно докато кученцето бъде 
осиновено

```python
buy_food = int(input()) * 1000
eat_day = input()
while eat_day != 'Adopted':
    buy_food -= int(eat_day)
    eat_day = input()
if buy_food < 0:
    print(f'Food is not enough. You need {-buy_food} grams more.')
else:
    print(f'Food is enough! Leftovers: {buy_food} grams.')
```

---
# Задача 6 - Eastern Competition

С наближаването на Великден, пекарна организира конкурс за направата на най-хубав козунак. 
Напишете програма, която да намира сладкаря с най-висок резултат. В началото на конкурса се 
въвежда броя на козунаците, които ще бъдат дегустирани от посетителите на пекарната, като за 
всеки козунак различен брой посетители, ще дадат оценка от 1 до 10.

```python
bake = int(input())
points = 0
max_points = 0
winner_chef = ''
for i in range (0, bake):
    chef = input()
    inp = input()
    while inp != 'Stop':
        points += int(inp)
        inp = input()
    print(f'{chef} has {points} points.')
    if points > max_points:
        max_points = points
        winner_chef = chef
        print(f'{chef} is the new number 1!')
    points = 0
print(f'{winner_chef} won competition with {max_points} points!')
```

