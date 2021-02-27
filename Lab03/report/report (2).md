﻿---
# Front matter
lang: ru-RU
title: "Лабораторная работа 3"
subtitle: "Математическое моделирование"
author: "Якушнвич Артём Юрьевич
teacher: "Кулябов Дмитрий Сергеевич"

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

Рассмотреть модель боевых действий Ланчестера.

# Задание

## 1. Построить графики изменения численности войск армии Х и армии У для модели боевых действий между регулярными войсками.
## 2. Построить графики изменения численности войск армии Х и армии У для модели ведения боевых действий с участием регулярных войск и партизанских отрядов.

# Выполнение лабораторной работы

## Рассуждения и условие 

1. Рассмотрим простейшую модель боевых действий Ланчестера. Рассмотрим два случая ведения боевых действий:

- Боевые действия между регулярными войсками.

- Боевые действия с участием регулярных войск и партизанских отрядов.

2. Между страной Х и страной У идет война. Численность состава войск исчисляется от начала войны, и являются временными функциями x(t) и y(t). В начальный момент времени страна Х имеет армию численностью 50 000 человек, а в распоряжении страны У армия численностью в 69 000 человек. Для упрощения модели считаем, что коэффициенты a, b, c, h постоянны. Также считаем, что P(t) и Q(t) непрерывные функции.

3. Графики численности войск необходимы для следующих случаев:

- Модель боевых действий между регулярными войсками 

$\frac{\text{d}x}{\text{d}t}= -0,34x(t)-0,72y(t)+\sin(t+10)$

$\frac{\text{d}y}{\text{d}t}= -0,89x(t)-0,43y(t)+\cos(t+20)$

- Модель ведение боевых действий с участием регулярных войск и партизанских отрядов

$\frac{\text{d}x}{\text{d}t}= -0,12x(t)-0,51y(t)+\sin(20t)$

$\frac{\text{d}y}{\text{d}t}= -0,3x(t)y(t)-0,61y(t)+\cos(13t)$

## Начальные условия

1. X - численность первой армии, Y - численность второй армии для моего варианта. (рис. -@fig:001)

![Численности армий](images\1.png){ #fig:001 width=70% }

2. Константы для боя между регулярными войсками:

a1 = 0.34 - константа, характеризующая степень влияния различных факторов на потери в бою между регулярными войсками;

b1 = 0.72 - эффективность боевых действий армии у в бою между регулярными войсками;

c1 = 0.89 - эффективность боевых действий армии х в бою между регулярными войсками;

h1 = 0.43 - константа, характеризующая степень влияния различных факторов на потери в бою между регулярными войсками. (рис. -@fig:002)

![Константы для боя между регулярными войсками](images\2.png){ #fig:002 width=70% }

3. Константы для боя между регулярными войсками и партизанскими отрядами:

a2 = 0.12 - константа, характеризующая степень влияния различных факторов на потери в бою между регулярными войсками и партизанскими отрядами;

b2 = 0.51 - эффективность боевых действий армии у в бою между регулярными войсками и партизанскими отрядами;

c2 = 0.3 - эффективность боевых действий армии х в бою между регулярными войсками и партизанскими отрядами;

h2 = 0.61 - константа, характеризующая степень влияния различных факторов на потери в бою между регулярными войсками и партизанскими отрядами. (рис. -@fig:003)

![Константы для боя между регулярными войсками и партизанскими отрядами](images\3.png){ #fig:003 width=70% }

4. Следующие строки описывают начальный момент времени (t0 = 0), предельный момент времени (tmax = 1) и шаг изменения времени (dt = 0.05). (рис. -@fig:004)

![Начальные условия времени](images\4.png){ #fig:004 width=70% }

## Составление систем дифференциальных уравнений и их решения

1. Просчитаем возможность подхода подкрепления к армии х (sin1) и к армии у (cos1) в бою между регулярными войсками. (рис. -@fig:005)

![Подход подкрепления, регулярные войска](images\5.png){ #fig:005 width=70% }

2. Просчитаем возможность подхода подкрепления к армии х (sin2) и к армии у (cos2) в бою между регулярным войском и партизанским отрядом. (рис. -@fig:006)

![Подход подкрепления, регулярное войско и партизанский отряд](images\6.png){ #fig:006 width=70% }

3. Составим системы дифференциальных уравнений изменения численностей первой армии и второй армии регулярных войск. (рис. -@fig:007)

![Изменения численностей армий регулярных войск](images\7.png){ #fig:007 width=70% }

4. Составим системы дифференциальных уравнений изменения численностей армии регулярных войск и партизанского отряда. (рис. -@fig:008)

![Изменения численностей армии регулярного войска и партизанского отряда](images\8.png){ #fig:008 width=70% }

5. Следующие строки задают вектор начальных условий (v) и считают решения дифференциальных уравнений (u1 и u2). (рис. -@fig:009)

![Вектор начальных условий и решения дифференциальных уравнений](images\9.png){ #fig:009 width=70% }

## Построение графиков решений

1. Эти строки строят график для модели боевых действий между регулярными войсками. (рис. -@fig:010)

![Построение графика боя регулярных войск](images\10.png){ #fig:010 width=70% }

2. Так выглядит график для модели боевых действий между регулярными войсками. (рис. -@fig:011)

![График боя регулярных войск](images\11.png){ #fig:011 width=70% }

3. Эти строки строят график для модели боевых действий между регулярным войском и партизанским отрядом. (рис. -@fig:012)

![Построение графика боя регулярного войска и партизанского отряда](images\12.png){ #fig:012 width=70% }

4. Так выглядит график для модели боевых действий между регулярным войском и партизанским отрядом. (рис. -@fig:013)

![График боя регулярного войска и партизанского отряда](images\13.png){ #fig:013 width=70% }

# Выводы

В результате выполнения третьей лабораторной работы, я рассмотрела один из примеров простейшей модели боевых действий – модель Ланчестера. 
