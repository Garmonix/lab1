---
# Front matter
lang: ru-RU
title: "Лабораторная работа 2"
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
mainfont: Calibri
romanfont: Calibri
sansfont: Calibri
monofont: Calibri
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

Рассмотреть один из примеров построения математических моделей для выбора правильной стратегии при решении задач поиска.

# Задание

## 1. Запись уравнения, описывающего движение катера, с начальными условиями для двух случаев
## 2. Построение траектории движения катера и лодки для двух случаев
## 3. Нахождение точки пересечения траектории катера и лодки 

# Выполнение лабораторной работы

### Рассуждения и вывод дифференциальных уравнений

### 1. Принимаем за $t_{0}=0, x_{л0}=0$ - место нахождения лодки браконьеров в момент обнаружения, $x_{к0}=k$ - место нахождения катера береговой охраны относительно лодки браконьеров в момент обнаружения лодки.

### 2. Введем полярные координаты. Считаем, что полюс - это точка обнаружения лодки браконьеров $x_{л0}(\theta =x_{л0}=0)$, а полярная ось r проходит через точку нахождения катера береговой охраны (рис. -@fig:001)

![Положение катера и лодки в начальный момент времени](Images\1.png){ #fig:001 width=70% }

### 3. Траектория катера должна быть такой, чтобы и катер, и лодка все время были на одном расстоянии от полюса $\theta$, только в этом случае траектория катера 
пересечется с траекторией лодки. Поэтому для начала катер береговой охраны должен двигаться некоторое время прямолинейно, пока не окажется на том же расстоянии от полюса, 
что и лодка браконьеров. После этого катер береговой охраны должен двигаться вокруг полюса удаляясь от него с той же скоростью, что и лодка браконьеров.
### 4. Чтобы найти расстояние x (расстояние после которого катер начнет двигаться вокруг полюса), необходимо составить простое уравнение. Пусть через время t катер и лодка окажутся 
на одном расстоянии x от полюса. За это время лодка пройдет x, а катер $k-x$ (или $k+x$, в зависимости от начального положения катера относительно полюса). Время, за которое они пройдут это 
расстояние, вычисляется как $\frac{x}{v}$ или $\frac{k-x}{2v}$ (во втором случае $\frac{x+k}{2v}$). Так как время одно и то же, то эти величины одинаковы. Тогда неизвестное расстояние x можно найти из следующего уравнения:
$\frac{x}{v}=\frac{k-x}{2v}$ в первом случае или $\frac{x}{v}=\frac{k+x}{2v}$ во втором. Отсюда мы найдем два значения $x_{1}=\frac{k}{3}$ и $x_{2}=k$, задачу будем решать для двух случаев.
### 5. После того, как катер береговой охраны окажется на одном расстоянии от полюса, что и лодка, он должен сменить прямолинейную траекторию и начать двигаться вокруг полюса удаляясь от него со скоростью лодки v. 
Для этого скорость катера раскладываем на две составляющие: $v_{r}$ - радиальная скорость и $v_{\tau}$ - тангенциальная скорость. (рис. -@fig:002)

![Разложение скорости катера](Images\2.png){ #fig:002 width=70% }

Радиальная скорость - это скорость, с которой катер удаляется от полюса, $v_{r}=\frac{\text{d}r}{\text{d}t}$. Нужно, чтобы эта скорость была равна скорости лодки, поэтому полагаем $\frac{\text{d}r}{\text{d}t}=v$. Тангенциальная скорость – это линейная скорость вращения катера относительно полюса. Она равна произведению угловой скорости $\frac{\text{d}\theta}{\text{d}t}$ на радиус r, $v_{\tau}=r\frac{\text{d}\theta}{\text{d}t}$. Из рисунка видно: $v_{\tau}=\sqrt{4v^{2}-v^{2}}=\sqrt{3}v$ (учитывая, что радиальная скорость равна v). Тогда получаем $r\frac{\text{d}\theta}{\text{d}t}=\sqrt{3}v$.
### 6. Решение исходной задачи сводится к решению системы из двух дифференциальных уравнений $\begin{cases} \frac{\text{d}r}{\text{d}t} = v\\ r\frac{\text{d}\theta}{\text{d}t} = \sqrt{3}v\end{cases}$ с начальными условиями $\begin{cases} \theta_{0}=0\\ r_{0}=x_{1}\end{cases}$ или $\begin{cases} \theta_{0}=-\pi\\ r_{0}=x_{2}\end{cases}$. Исключая из полученной системы производную по t, можно перейти к следующему уравнению: $\frac{\text{d}r}{\text{d}\theta}=\frac{r}{\sqrt{3}}$ Начальные условия остаются прежними. Решив это уравнение, вы получите траекторию движения катера в полярных координатах.

## Построение траектории движения катера и лодки для двух случаев и точки пересечения

Задам расстояние своего варинта k=17.4 и константу $fi=\frac{3 \pi}{4}$. (рис. -@fig:003)

![Константа](Images\3.png){ #fig:003 width=70% }

Следующие строки описывают движение катера охранников. (рис. -@fig:004)

![Движение катера охранников](Images\4.png){ #fig:004 width=70% }

Для первого случая зададим r0 и решим дифференциальное уравнение. (рис. -@fig:005)

![Первый случая](Images\5.png){ #fig:005 width=70% }

Для второго момента зададим r0_2 и решим дифференциальное уравнение.(рис. -@fig:007)

![Второй случая](Images\6.png){ #fig:007 width=70% }

Следующие строки описывают движение лодки браконьеров и перевод декартовые координаты в полярные. (рис. -@fig:009)

![Движение лодки браконьеров и полярные коорлинаты](Images\7.png){ #fig:009 width=70% }

Далее строим график. Движение охраны и браконьеров для первого случая. (рис. -@fig:011)

![График для первого случая](Images\8.png){ #fig:011 width=70% }

А этот - движение охраны и браконьеров для второго случая. (рис. -@fig:012)

![График для второго случая](Images\9.png){ #fig:012 width=70% }


# Выводы

Я научился решать задачу о погоне на примере построения математической модели на языке Python а также взаимодействовать с проэктом Jupyter.

