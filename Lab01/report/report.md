---
# Front matter
lang: ru-RU
title: "Отчёт по лабораторной работе"
subtitle: "Простейший вариант"
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

Освежить в памяти работу с гитом и терминалом git bush  а также познакомиться
с основными возможностями разметки Markdown.


# Задание

##Создать аккаунт на Github.
##Создать репозиторий.
##Настроить SSH keys.
##Настроить Git Bash.
##Добавить файл на Github.
##Сделать и приложить отчёт.

# Выполнение лабораторной работы

##Создал аккаунт на Github. (рис. -@fig:001)

![Профиль на Git](image/1.png){ #fig:001 width=70% }

##Создал репозиторий на Github. (рис. -@fig:002)

![Репозиторий на Git](image/2.png){ #fig:002 width=70% }

##Создал и подключил SSH-ключ. (рис. -@fig:003)

![SSH-key на Git](image/3.png){ #fig:003 width=70% }

##Настроил Git Bash. (рис. -@fig:004)

![Настройка git bash](image/4.png){ #fig:004 width=70% }

##Добавил первый файл на Github. (рис. -@fig:005)

![Первый файл на Git 1](image/5.png){ #fig:005 width=70% }

##Сделал отчёт в Markdown и залил на Git. 

# Выводы

Вспомнил основы работы с Git, научился создавать отчёты в Markdown.
