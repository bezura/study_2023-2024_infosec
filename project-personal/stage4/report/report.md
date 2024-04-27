---
## Front matter
title: "Отчет по индивидуальному проекту 4"
subtitle: "Дисциплина: Информационная безопасность"
author: "Хрусталев Влад Николаевич"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Знакомство с базовым сканером безопасности nikto.

# Выполнение лабораторной работы

1. Посмотим основную информацию об данном ПО и посмотрим возможные аргументы для команды ``` nikto -h ```.

![Вывод команды "nikto -h"](image/1.jpg){ #fig:001 width=70% }

2. Протестируем его на сайте моей разработки ``` nikto -h vsosh.rudn.ru```.

![Вывод команды "nikto -h vsosh.rudn.ru"](image/2.jpg){ #fig:002 width=70% }

3. Так же протестируем на поднятом уязвимом сервере ``` nikto -h 127.0.0.1/DVWA```.

![Вывод команды "nikto -h 127.0.0.1/DVWA"](image/3.jpg){ #fig:003 width=70% }

# Выводы

В результате выполнения лабораторной работы на практике опробовали базовым сканером безопасности nikto.