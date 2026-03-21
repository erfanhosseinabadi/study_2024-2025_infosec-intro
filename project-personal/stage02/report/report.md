---
## Front matter
title: "Отчёт по индивидуальному проекту этап 2"
subtitle: "Установка DVWA"
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
mathfont: Latin Modern Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions: Scale=MatchLowercase

## Biblatex
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

Получить практические навыки по установке DVWA.

# Задание

1. Установить DVWA.

# Выполнение лабораторной работы

Открываю GitHub, нахожу репозиторий DVWA и копирую его ссылку.

![репзиторий DVWA ](image/1.png){#fig:001 width=70%}

Открываю терминал, командой cd вхожу в директорию html (здесь хранятся файлы локального хоста) и клонирую репозиторий.

![Клонирование DVWA в /html](image/2.png){#fig:002 width=70%}

С помощью ls проверяю, что клонирование прошло успешно, затем с помощью chmod -R 777 разрешаю все права на все файлы в директории DVWA.

![chmod -R 777](image/3.png){#fig:003 width=70%}

Проверяю работу и захожу в dvwa/config, чтобы настроить веб-приложение.

![директория config](image/4.png){#fig:004 width=70%}

Затем копирую config.inc.php — файл с настройками конфигурации приложения.

![копирование config.int.php](image/5.png){#fig:005 width=70%}

В этом файле изменяю пароль, имя пользователя на  mwaku и создаю базу данных waku и сохраняю изменения.

![редактирование файла конфигурации](image/6.png){#fig:006 width=70%}

Запускаю службу MySQL командой start mysql и проверяю, что она работает, с помощью status mysql.

![Запуск mysql](image/7.png){#fig:007 width=70%}

![прверка работы mysql](image/8.png){#fig:008 width=70%}

Далее я вхожу в mmysql используя mysql -u root -p 

![вход в mysql](image/9.png){#fig:009 width=70%}

Создаю базу данных teo и нового пользователя используя create user 'teofa'@'127.0.0.1' identified by 'password'. Используя эту команду, создала пользователя teofa, работаюшего на сервер локального хоста (127.0.0.1) и пароль password.

![создание пользоателя](image/10.png){#fig:010 width=70%}

Предоставляю этому пользователю все права на базу данных и завершаю работу.

![Разрешение права](image/11.png){#fig:011 width=70%}

Запускаю сервер apache2.

![Запуск apache2](image/12.png){#fig:012 width=70%}

Далее вхожу в /etc/php/8.4. 

![вход в /etc/php/8.4](image/13.png){#fig:013 width=70%}

Включаю значения allow_url_fopen и allow_url_include в файле apache2/php.ini.

![Включение  allow_url](image/14.png){#fig:014 width=70%}

Перезапускаю сервер Apache2 с помощью systemctl restart apache2.

![Перезапуск apache2](image/15.png){#fig:015 width=70%}

Открою 127.0.0.1./DVWA/setup.php в браузере.

![страница веб-приложения](image/16.png){#fig:016 width=70%}

Нажимаю кнопку Create/Reset Database. Происходит создание базы данных, и автоматически выполняется переход на страницу входа. Для входа использую учетные данные: логин admin, пароль password

![Вход в DVWA](image/17.png){#fig:017 width=70%}

После входа попадаю на домашнюю страницу DVWA.

![Домшняя страница dvwa](image/18.png){#fig:018 width=70%}

# Выводы

В результате работы я получила навыки по установке DVWA.

