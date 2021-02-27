---
# Front matter
lang: ru-RU
title: "Лабораторная работа 3"
subtitle: "Математическое моделирование"
author: "Якушевич Артём Юрьевич"
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

## Условия задачи

1. Рассмотрим модель боевых действий Ланчестера. В противоборстве будут принимать участие как регулярные войска, так и партизанские отряды. Рассмотрим два случая ведения боевых действий:

- Боевые действия между регулярными войсками.

- Боевые действия с участием регулярных войск и партизанских отрядов.

2. Между страной Х и страной У идет война. Численность состава войск исчисляется от начала войны, и являются временными функциями x(t) и y(t). 
В начальный момент времени страна Х имеет армию численностью 222 000 человек, а в распоряжении страны У армия численностью в 229 000 человек. 
Для упрощения модели считаем, что коэффициенты a, b, c, h постоянны. 

3. Графики численности войск необходимы для следующих случаев:

- Модель боевых действий между регулярными войсками 

$\frac{\text{d}x}{\text{d}t}= -0.223x(t) - 0.774y(t) + sin(t+1)$

$\frac{\text{d}y}{\text{d}t}= -0.665x(t) - 0.332y(t) + cos(t+2)$

- Модель ведение боевых действий с участием регулярных войск и партизанских отрядов

$\frac{\text{d}x}{\text{d}t}= -0.291x(t) - 0.865y(t) + |sin(2t)|$$

$\frac{\text{d}y}{\text{d}t}= -0.456x(t)y(t) - 0.789y(t) + |cos(t)|$

## Данные задачи

1. X - численность первой армии, Y - численность второй армии. a1 a2 b1 b2 c1 c2 h1 h2 - константы для боя между регулярными войсками (рис. -@fig:001)

![Условия задачи](images\1.png){ #fig:001 width=70% }

4. Начальный момент времени (t0 = 0), предельный момент времени (tmax = 1) и шаг изменения времени (dt = 0.05). (рис. -@fig:002)

![Начальные условия времени](images\2.png){ #fig:002 width=70% }

## Решение систем дифференциальных уравнений 

1. Просчитаем возможность подхода подкрепления к армии х (Sin1) и к армии у (Cos1) в бою между регулярными войсками. (рис. -@fig:003)

![Первый случай](images\3.png){ #fig:003 width=70% }

2. Просчитаем возможность подхода подкрепления к армии х (Sin2) и к армии у (Cos2) в бою между регулярным войском и партизанским отрядом. (рис. -@fig:004)

![Второй случай](images\4.png){ #fig:004 width=70% }

3. Система дифференциальных уравнений изменения численностей первой армии и второй армии регулярных войск. (рис. -@fig:005)

![Первый случай](images\5.png){ #fig:005 width=70% }

4. Система дифференциальных уравнений изменения численностей армии регулярных войск и партизанского отряда. (рис. -@fig:006)

![Второй случай](images\6.png){ #fig:006 width=70% }

5. Следующие строки задают вектор начальных условий (v) (рис. -@fig:007)

![Вектор начальных условий и решения дифференциальных уравнений](images\7.png){ #fig:007 width=70% }

## Построение графиков решений 

1.  Решения дифференциальных уравнений (r1 и r2). График для модели боевых действий между регулярными войсками. (рис. -@fig:008)

![График боя регулярных войск](images\8.png){ #fig:008 width=70% }

3. График для модели боевых действий между регулярным войском и партизанским отрядом. (рис. -@fig:009)

![График боя регулярного войска и партизанского отряда](images\9.png){ #fig:009 width=70% }

# Выводы

В результате выполнения третьей лабораторной работы, я рассмотрел один из примеров модели боевых действий Ланчестера. 

