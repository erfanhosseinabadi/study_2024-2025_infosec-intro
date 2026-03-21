---
## Front matter
lang: ru-RU
title: Структура по индивидуальному проекту этап 2
subtitle: Установка DVWA
author:
  - Гомес Лопес Теофания
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 20 03 2026

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: default
header-includes:
 #- \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цель работы

Получить практические навыки по установке DVWA.

# Задание

1. Установить DVWA.

# Выполнение лабораторной работы

## репзиторий DVWA

Открываю GitHub, нахожу репозиторий DVWA и копирую его ссылку.

![репзиторий DVWA ](image/1.png){#fig:001 width=70%}

## Клонирование DVWA в /html

Открываю терминал, командой cd вхожу в директорию html (здесь хранятся файлы локального хоста) и клонирую репозиторий.

![Клонирование DVWA в /html](image/2.png){#fig:002 width=70%}

## chmod -R 777

С помощью ls проверяю, что клонирование прошло успешно, затем с помощью chmod -R 777 разрешаю все права на все файлы в директории DVWA.

![chmod -R 777](image/3.png){#fig:003 width=70%}

## копирование config.int.php

Затем копирую config.inc.php — файл с настройками конфигурации приложения.

![копирование config.int.php](image/5.png){#fig:005 width=70%}

## редактирование файла конфигурации

В этом файле изменяю пароль, имя пользователя на  mwaku и создаю базу данных waku и сохраняю изменения.

![редактирование файла конфигурации](image/6.png){#fig:006 width=70%}

## проверка работы mysql

![прверка работы mysql](image/8.png){#fig:008 width=70%}

## вход в mysql

Далее я вхожу в mmysql используя mysql -u root -p 

![вход в mysql](image/9.png){#fig:009 width=70%}

## создание пользоателя

Создаю базу данных teo и нового пользователя используя create user 'teofa'@'127.0.0.1' identified by 'password'. Используя эту команду, создала пользователя teofa, работаюшего на сервер локального хоста (127.0.0.1) и пароль password.

![создание пользоателя](image/10.png){#fig:010 width=70%}

## Разрешение права

Предоставляю этому пользователю все права на базу данных и завершаю работу.

![Разрешение права](image/11.png){#fig:011 width=70%}

## вход в /etc/php/8.2

Далее вхожу в /etc/php/8.4. 

![вход в /etc/php/8.4](image/13.png){#fig:013 width=70%}

## Включение  allow_url

Включаю значения allow_url_fopen и allow_url_include в файле apache2/php.ini.

![Включение  allow_url](image/14.png){#fig:014 width=70%}

## Перезапуск apache2

Перезапускаю сервер Apache2 с помощью systemctl restart apache2.

![Перезапуск apache2](image/15.png){#fig:015 width=70%}

## страница веб-приложения

Открою 127.0.0.1./DVWA/setup.php в браузере.

![страница веб-приложения](image/16.png){#fig:016 width=70%}

## Вход в DVWA

Нажимаю кнопку Create/Reset Database. Происходит создание базы данных, и автоматически выполняется переход на страницу входа. Для входа использую учетные данные: логин admin, пароль password

![Вход в DVWA](image/17.png){#fig:017 width=70%}

## Домшняя страница dvwa

После входа попадаю на домашнюю страницу DVWA.

![Домшняя страница dvwa](image/18.png){#fig:018 width=70%}


# Выводы

В результате работы я получила навыки по установке DVWA.