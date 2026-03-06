---
## Front matter
title: "Отчёт по индивидуальному проекту этап 1"
subtitle: "Установка Kali Linux"
author: "Ерфан Хосейнабади"

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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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

Я научился устанавливать операционные системы на виртуальные машины.

# Задание

Установить дистрибутив Linux.

# Выполнение лабораторной работы

Я запускаю VirtualBox и создаю новую виртуальную машину.

![Название машины](image/1.png){#fig:001 width=70%}

Дальше нужно создать виртуальный диск и настроить оперативную память

![Создание виртуального диска](image/2.png){#fig:002 width=70%}

![Объем оперативной памяти](image/3.png){#fig:003 width=70%}

Потом я подтверждаю настройки и запускаю виртуальную машину.

![Итог](image/4.png){#fig:004 width=70%}

Выбираю install чтобы начать установка

![Окно установки](image/5.png){#fig:005 width=70%}

При этом я вижу, что образ диска уже подключен к носителю.

![Подключенный образ](image/6.png){#fig:006 width=70%}

Далее выбираю все по моему хотению: Язык установки - английский;

![язык установки](image/7.png){#fig:007 width=70%}

Локация - Европа;

![Локация](image/8.png){#fig:008 width=70%}

конфигурация клавиатуры (язык).

![конфигурация клавиатуры](image/9.png){#fig:009 width=70%}

Теперь я настраиваю сеть. В качестве имени я указываю своё.

![Настройки сети](image/10.png){#fig:010 width=70%}

Я создаю нового пользователя, придумываю для него пароль и настраиваю часовой пояс.

![Создание пользователя](image/11.png){#fig:011 width=70%}

![Установка пароля](image/12.png){#fig:012 width=70%}

![Настройки часов](image/13.png){#fig:013 width=70%}

Я выбираю диск для работы и сохраняю настройки.

![Выбор диска](image/14.png){#fig:0014 width=70%}

Далее все настройки сохраняю и устанавливаю систему.

![Установка системы](image/15.png){#fig:015 width=70%}

Теперь нужно выбрать рабочий стол  и закончить установку.

![Выбор UI](image/16.png){#fig:016 width=70%}

![Завершение установки](image/17.png){#fig:017 width=70%}

![Домашний экран](image/18.png){#fig:018 width=70%}

Я проверяю, что образ диска отключился. Значит, всё установилось правильно.

![Пустой носитель](image/19.png){#fig:019 width=70%}


# Выводы

Я научилась устанавливать ОС на виртуальные машины.