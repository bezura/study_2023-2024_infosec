---
## Front matter
title: "Отчет по лабораторной работе 6"
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

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux. Проверить работу SELinx на практике совместно с веб-сервером Apache.

# Выполнение лабораторной работы

1. Сделаем подготовительные операции перед работой (рис. [-@fig:001] и [-@fig:002])

![Проверка статуса SeLinux](image/2.jpg){ #fig:002 width=70% }

![Проверка статуса httpd](image/1.jpg){ #fig:001 width=70% }

2. Определение контекста безопасности и попытка проверки наличия команды StInfo. +sestatus команды не существтует. (рис. [-@fig:003] и [-@fig:004] и [-@fig:004])

![Просмотр контекста безопасности httpd](image/3.jpg){ #fig:003 width=70% }

![Текущее состояние переключателей SELinux для Apache](image/4.jpg){ #fig:004 width=70% }

![StInfo](image/5.jpg){ #fig:005 width=70% }

3. Определение типов файлов в диреекториях Apache (файлов серервера) (рис. [-@fig:006] и [-@fig:007])

![Тип файлов и поддиректорий, находящихся в директории /var/www](image/6.jpg){ #fig:006 width=70% }

![Тип файлов и поддиректорий, находящихся в директории /var/www/html](image/7.jpg){ #fig:007 width=70% }

4. Создание html файла, проверка его контекста и визуальный просмотр (рис. [-@fig:008] и [-@fig:009] и [-@fig:010])

![Создание html-файл /var/www/html/test.html ](image/8.jpg){ #fig:008 width=70% }

![Контекст созданного файла](image/9.jpg){ #fig:009 width=70% }

![Отображение на сайте](image/10.jpg){ #fig:010 width=70% }

5. Просмотр инфо о команде httpd_selinux -- она отсутвует (рис. [-@fig:011])

![man httpd_selinux](image/11.jpg){ #fig:011 width=70% }

6. Изменение конктекста html файла на любой другой и попытка просмотра. У нес нет доступа. Так же проверим логи. (рис. [-@fig:012] и [-@fig:013] и [-@fig:014])

![Измените контекст файла /var/www/html/test.html](image/12.jpg){ #fig:012 width=70% }

![Отображение на сайте с изменённые контекстом файла](image/13.jpg){ #fig:013 width=70% }

![Просмотр логов](image/14.jpg){ #fig:014 width=70% }

7. Проведём доп изменения. Изменим прослушиваемый порт сервреа на 81 и перезапустим веб-сервер. Ошибок у нас нет, так как я ранее пользовался тут Apache и порт 81 прописал в разрешённые. Поэтому команда добавления в разрешённые тут была излишняя (рис. [-@fig:015] и [-@fig:016] и [-@fig:017])

![Изменение прослушиваемого порта Apache на 81](image/15.jpg){ #fig:015 width=70% }

![Перезапуск Apache](image/16.jpg){ #fig:016 width=70% }

![Добавление порта 81 в разорешённые](image/17.jpg){ #fig:017 width=70% }

8. Вернём всё обратно. Проверим что всё отображается. И попытаемся отключить порт 81, но не выйдет так как он уже используется и прописан в другом месте (рис. [-@fig:021] и [-@fig:018] и [-@fig:019] и [-@fig:020])

![Возврат стандарт контекста](image/18.jpg){ #fig:018 width=70% }

![Проверка сайта](image/18.jpg){ #fig:021 width=70% }

![Возврат стандартного порта](image/19.jpg){ #fig:019 width=70% }

![Попытка отключения порта 81](image/20.jpg){ #fig:020 width=70% }

# Выводы

На данной лабораторной работе мы развили навыки администрирования ОС Linux, получили первое практическое знакомство с технологией SELinux.