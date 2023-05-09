# Задача 1 - Cinema

В една кинозала столовете са наредени в правоъгълна форма в r реда и c колони. Има три вида прожекции с билети на различни цени:
+	Premiere - премиерна прожекция, на цена 12.00 лева;
+	Normal - стандартна прожекция, на цена 7.50 лева;
+	Discount - прожекция за деца, ученици и студенти на намалена цена от 5.00 лева.
Напишете програма, която чете тип прожекция (текст), брой редове и брой колони в залата (цели числа), въведени от потребителя, и изчислява общите приходи от билети при пълна зала. Резултатът да се отпечата във формат 2 знака след десетичната точка.  


```python
print ('Hello SoftUni')
```

---
# Задача 2 - Summer Outfit

В една кинозала столовете са наредени в правоъгълна форма в r реда и c колони. Има три вида прожекции с билети на различни цени:
+	Premiere - премиерна прожекция, на цена 12.00 лева;
+	Normal - стандартна прожекция, на цена 7.50 лева;
+	Discount - прожекция за деца, ученици и студенти на намалена цена от 5.00 лева.
Напишете програма, която чете тип прожекция (текст), брой редове и брой колони в залата (цели числа), въведени от потребителя, и изчислява общите приходи от билети при пълна зала. Резултатът да се отпечата във формат 2 знака след десетичната точка.  


```python
print (1)
print (2)
print (3)
print (4)
print (5)
print (6)
print (7)
print (8)
print (9)  
print (10)
```

---
# Задача 3 - New House

Да се напише конзолна програма, която въвежда две цели числа (страните на правоъгълника a и b) и пресмята лицето на правоъгълник с тези страни.

```python
a = int(input())
b = int(input())
print (a * b)
```

---
# Задача 4 - Fishing Boat

Да се напише програма, която чете от конзолата реално число и го преобразува от инчове в сантиметри. За целта умножете инчовете по 2.54 (1 инч = 2.54 сантиметра).

```python
a = float(input())
print(a * 2.54)
```

---
# Задача 5 - Journey

Да се напише програма, която чете от конзолата текст (име на човек) и отпечатва "Hello, &lt;name&gt;!", където name е въведеното име от конзолата.

```python
name = input()
print('Hello,' + name + '!')
```

---
# Задача 6 - Operations Between Numbers

Напишете програма, която прочита от конзолата име, фамилия, възраст и град и печата следното съобщение: "You are &lt;firstName&gt; &lt;lastName&gt;, a &lt;age&gt;-years old person from &lt;town&gt;."

```python
first_name = input()
last_name = input()
age = input()
town = input()
print(f'You are {first_name} {last_name}, a {age}-years old person from {town}.')
```

---
# Задача 7 - Hotel Room

Напишете програма, която изчислява колко часа ще са необходими на един архитект, за да изготви проектите на няколко строителни обекта. Изготвянето на един проект отнема три часа.

```python
architect = input()
projects = int(input())
print(f'The architect {architect} will need {projects * 3} hours to complete {projects} project/s.')
```

---
# Задача 8 - On Time for the Exam

Напишете програма, която пресмята нужните разходи за закупуването на храна за кучета и котки.  Храната се пазарува от зоомагазин, като една опаковка храна за кучета е на цена 2.50 лв, а опаковка храна за котки струва 4 лв.

```python
food_dog = int(input())
food_cat = int(input())
print(f'{food_dog * 2.50 + food_cat * 4} lv.')
```

---
# Задача 9 - Ski Trip

Божидара разполага с няколко къщи на Черноморието и желае да озелени дворовете на някои от тях, като по този начин създаде уютна обстановка и комфорт на гостите си. За целта е наела фирма.<br>
Напишете програма, която изчислява необходиматa сума, които Божидара ще трябва да заплати на фирмата изпълнител на проекта. Цената на един кв. м. е 7.61 лв със ДДС. Понеже нейният двор е доста голям, фирмата изпълнител предлага 18% отстъпка от крайната цена.


```python
size = float(input())
print(f'The final price is: {size * 7.61 - size * 7.61 * 0.18} lv.')
print(f'The discount is: {size * 7.61 * 0.18} lv.')
```