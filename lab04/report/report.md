---
# Front matter
lang: ru-RU
title: "Лабораторная работа №4"
subtitle: "Модель гармонических колебаний"
author: "Якушевич Артём Юрьевич"

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Рассмотреть фазовый портрет гармонического осциллятора и решить уравнения гармонического осциллятора для следующих случаев

На интервале $t \in [0; 45]$(шаг 0.05) с начальными условиями $x_0 = 0.9, y_0 = 0.9$

# Теоретическая справка

## Уравнение свободных колебаний
Уравнение свободных колебаний гармонического осциллятора имеет следующий вид:
$$ \ddot {x} + 2 \gamma \dot {x} + w_0^2x = f(t) $$

$w$ — частота

$\gamma$ — затухание


# Задание

## 1. Построить решение уравнения гармонического осциллятора без затухания.
## 2. Записать уравнение свободных колебаний гармонического осциллятора с затуханием, построить его решение. Построить фазовый портрет гармонических колебаний с затуханием.
## 3. Записать уравнение колебаний гармонического осциллятора, если на систему действует внешняя сила, построить его решение. Построить фазовый портрет колебаний с действием внешней силы.

# Выполнение лабораторной работы
# Стандартные библиотеки

import math
import numpy as np
from scipy.integrate import odeint
import matplotlib.pyplot as plt

# Первый случай (рис. -@fig:001)

![Первый случай](images/1.png){ #fig:001 width=70% }


# Запишем правую часть уравнения (рис. -@fig:002)

![Уравнение](images/2.png){ #fig:002 width=70% }

# Далее запишем вектор-функцию f(t, x) для решения системы дифференциальных уравнений x' = y(t, x)(рис. -@fig:003)

![Вектор-функция](images/3.png){ #fig:003 width=70% }

# Так выглядит вектор начальных условий x(t0) = x0 x' = y(t, x)(рис. -@fig:004)

![вектор начальных условий](images/4.png){ #fig:004 width=70% }

# Интервал, на котором будет решаться задача (рис. -@fig:005)

![Интервал](images/5.png){ #fig:005 width=70% }

# Решаем дифференциальные уравнения с начальным условием x(t0) = x0 на интервале t с правой частью, 
заданной y и записываем решение в матрицу x (рис. -@fig:006)

![дифференциальные уравнения](images/6.png){ #fig:006 width=70% }

# записываем y1 y2 (рис. -@fig:007)
y1 = x[:,0]

![y1 y2](images/7.png){ #fig:007 width=70% }

plt.plot(y1,y2)
plt.grid(axis='both')



# Для второго случая (рис. -@fig:008)

![Второй случай](images/8.png){ #fig:008 width=70% }


# Запишем правую часть уравнения (рис. -@fig:009)

![правая часть уравнения](images/9.png){ #fig:009 width=70% }

# далее запишем вектор-функцию f(t, x) для решения системы дифференциальных уравнений x' = y(t, x) (рис. -@fig:010)

![вектор-функция](images/10.png){ #fig:010 width=70% }

# Так выглядит вектор начальных условий x(t0) = x0 (рис. -@fig:011)

![Вектор начальных условий](images/11.png){ #fig:011 width=70% }

# Так выглядит интервал, на котором будет решаться задача (рис. -@fig:012)

![Интервал](images/12.png){ #fig:012 width=70% }

# Решаем дифференциальные уравнения с начальным условием x(t0) = x0 на интервале t с правой частью, 
заданной y и записываем решение в матрицу x (рис. -@fig:013)

![Рещение диф уравнения и матрица](images/13.png){ #fig:013 width=70% }

# Переписываем отдельно yy1 и yy2 (рис. -@fig:014)

![yy1 и yy2](images/14.png){ #fig:014 width=70% }




# И наконец третий случай (рис. -@fig:015)

![третий случай](images/15.png){ #fig:015 width=70% }

# Запишем правуб часть уравнения (рис. -@fig:016)

![Правая часть уравнения](images/16.png){ #fig:016 width=70% }


# Так выглядим вектор-функция f(t, x) для решения системы дифференциальных уравнений x' = y(t, x) (рис. -@fig:017)

![Вектор-функция](images/17.png){ #fig:017 width=70% }


# Вектор начальных условий x(t0) = x0 (рис. -@fig:018)

![Вектор-функция](images/18.png){ #fig:018 width=70% }


# Интервал, на котором будет решаться задача (рис. -@fig:019)

![Интервал](images/19.png){ #fig:019 width=70% }

# Решаем дифференциальные уравнения с начальным условием x(t0) = x0 на интервале t с правой частью, заданной y и записываем решение в матрицу x (рис. -@fig:020)

![Дифференциальные уравнения](images/20.png){ #fig:020 width=70% }

# Переписываем отдельно yyy1 и yyy2  (рис. -@fig:021)

![yyy1 и yyy2](images/21.png){ #fig:021 width=70% }

## Графики

График первого случая. Колебания гармонического осциллятора без затуханий и без действий внешней силы (рис. -@fig:022)

![Первый случай](images/22.png){ #fig:022 width=70% }

График второго случая. Колебания гармонического осциллятора c затуханием и без действий внешней силы (рис. -@fig:023)

![Второй случай](images/23.png){ #fig:023 width=70% }

График третьего случая. Колебания гармонического осциллятора c затуханием и под действием внешней силы (рис. -@fig:024)

![Третий случай](images/24.png){ #fig:024 width=70% }

## Ответы на вопросы 

### Запишите простейшую модель гармонических колебаний
Простейшим видом колебательного процесса являются простые гармонические колебания, которые описываются уравнением $x = x_m cos (ωt + φ0)$. 
    
### Дайте определение осциллятора
Осциллятор — система, совершающая колебания, то есть показатели которой периодически повторяются во времени.

### Запишите модель математического маятника

Уравнение динамики принимает вид: $$\frac{d^2 \alpha}{d t^2} + \frac{g}{L} sin{\alpha} = 0$$ В случае малых колебаний полагают $sin{\alpha} ≈ \alpha$. В результате возникает линейное дифференциальное уравнение $$\frac{d^2 \alpha}{d t^2} + \frac{g}{L} \alpha = 0$$ или $$\frac{d^2 \alpha}{d t^2} + \omega^2 \alpha = 0$$

### Запишите алгоритм перехода от дифференциального уравнения второго порядка к двум дифференциальным уравнениям первого порядка
Пусть у нас есть дифференциальное уравнение 2-го порядка:
$$ \ddot {x} + w_0^2x = f(t) $$

Для перехода к системе уравнений первого порядка сделаем замену (это метод Ранге-Кутты):
$$ y = \dot{x} $$

Тогда получим систему уравнений:
    $$ \begin{cases} y = \dot{x} \\ \dot{y} = - w_0^2x \end{cases}$$
    
### Что такое фазовый портрет и фазовая траектория?
Фазовый портрет — то, как величины, описывающие состояние системы (= динамические переменные), зависят друг от друга.
Фазовая траектория — кривая в фазовом пространстве, составленная из точек, представляющих состояние динамической системы в последовательные моменты времени в течение всего времени эволюции.

# Выводы

Я промоделировал фазовый портрет гармонического осциллятора и решил уравнения гармонического осциллятора для 3х случаев:
колебания гармонического осциллятора без затуханий и без действий внешней силы,
колебания гармонического осциллятора c затуханием и без действий внешней силы,
колебания гармонического осциллятора c затуханием и под действием внешней силы.