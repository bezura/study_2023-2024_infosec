---
## Front matter
lang: ru-RU
title: Презентация к лабораторной работе 6
subtitle: Основы информационной безопасности
author:
	Хрусталев Влад Николаевич
institute:
  - Российский университет дружбы народов им. Патриса Лумумбы, Москва, Россия

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'

## Fonts
mainfont: Arial
romanfont: Arial
sansfont: Arial
monofont: Arial
---

## Цель работы

Развить навыки администрирования ОС Linux. Получить первое практическое знакомство с технологией SELinux. Проверить работу SELinx на практике совместно с веб-сервером Apache.

## Сделаем подготовительные операции перед работой 

![Проверка статуса SeLinux](image/2.jpg){ #fig:002 width=70% }

![Проверка статуса httpd](image/1.jpg){ #fig:001 width=70% }

## Определение контекста безопасности и попытка проверки наличия команды StInfo. +sestatus команды не существтует.

![Просмотр контекста безопасности httpd](image/3.jpg){ #fig:003 width=70% }

![Текущее состояние переключателей SELinux для Apache](image/4.jpg){ #fig:004 width=70% }

![StInfo](image/5.jpg){ #fig:005 width=70% }

## Определение типов файлов в диреекториях Apache (файлов серервера)

![Тип файлов и поддиректорий, находящихся в директории /var/www](image/6.jpg){ #fig:006 width=70% }

![Тип файлов и поддиректорий, находящихся в директории /var/www/html](image/7.jpg){ #fig:007 width=70% }

## Создание html файла, проверка его контекста и визуальный просмотр

![Создание html-файл /var/www/html/test.html ](image/8.jpg){ #fig:008 width=70% }

![Контекст созданного файла](image/9.jpg){ #fig:009 width=70% }

![Отображение на сайте](image/10.jpg){ #fig:010 width=70% }

## Просмотр инфо о команде httpd_selinux -- она отсутвует

![man httpd_selinux](image/11.jpg){ #fig:011 width=70% }

## Изменение конктекста html файла на любой другой и попытка просмотра. У нес нет доступа. Так же проверим логи.

![Измените контекст файла /var/www/html/test.html](image/12.jpg){ #fig:012 width=70% }

![Отображение на сайте с изменённые контекстом файла](image/13.jpg){ #fig:013 width=70% }

![Просмотр логов](image/14.jpg){ #fig:014 width=70% }

## Проведём доп изменения. Изменим прослушиваемый порт сервреа на 81 и перезапустим веб-сервер. Ошибок у нас нет, так как я ранее пользовался тут Apache и порт 81 прописал в разрешённые. Поэтому команда добавления в разрешённые тут была излишняя

![Изменение прослушиваемого порта Apache на 81](image/15.jpg){ #fig:015 width=70% }

![Перезапуск Apache](image/16.jpg){ #fig:016 width=70% }

![Добавление порта 81 в разорешённые](image/17.jpg){ #fig:017 width=70% }

## Вернём всё обратно. Проверим что всё отображается. И попытаемся отключить порт 81, но не выйдет так как он уже используется и прописан в другом месте 

![Возврат стандарт контекста](image/18.jpg){ #fig:018 width=70% }

![Проверка сайта](image/18.jpg){ #fig:021 width=70% }

![Возврат стандартного порта](image/19.jpg){ #fig:019 width=70% }

![Попытка отключения порта 81](image/20.jpg){ #fig:020 width=70% }


# Выводы

На данной лабораторной работе мы развили навыки администрирования ОС Linux, получили первое практическое знакомство с технологией SELinux.
