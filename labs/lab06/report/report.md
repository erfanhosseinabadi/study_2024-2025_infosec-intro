---
## Front matter
title: "Отчёт по лабораторной работе 6"
subtitle: "Мандатное разграничение прав в Linux"
author: "Ерфан Хосейнабади"
lang: ru-RU
toc: true
toc-depth: 2
lof: true
lot: true
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
mainfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float}
  - \floatplacement{figure}{H}
  - \usepackage{caption}
  - \captionsetup{labelsep=period}
---
# Цель работы

Развить навыки администрирования ОС linux. Получить практическое знакомство с SELinux1. Проверить работу SELinux на практике совместно с веб-сервером Apache.


# Выполнение лабораторной работы

Сначала я вошла в систему под своим именем. Потом я проверила SELinux: с помощью getenforce и sestatus я увидела, что режим — enforcing, а политика — targeted.

![проверка режима работы SELinux](image/1.png){#fig:001 width=70%}

Сначала я запускаю Apache. Затем с помощью браузера я проверяю доступ к веб-серверу на моём компьютере — сервер отвечает. Команда service httpd status тоже показывает, что сервер работает.

![Проверка работы Apache](image/2.png){#fig:002 width=70%}

С помощью команды ps auxZ | grep httpd нашла веб-сервер Apache в списке процессов. Его контекст безопасности - httpd_t 

![Контекст безопасности Apache](image/3.png){#fig:003 width=70%}

Я проверила, какие настройки (булевы переключатели) SELinux включены для Apache.

![Состояние переключателей SELinux](image/4.png){#fig:004 width=70%}


С помощью команды ls -lZ /var/www я посмотрела типы поддиректорий в папке /var/www. Владелец всех директорий — root. Права на изменение есть только у владельца. Файлов в этой директории нет.

![Типы поддиректорий](image/6.png){#fig:006 width=70%}

В директории /var/www/html нет файлов. 

![Типы файлов](image/7.png){#fig:007 width=70%}

Создать файл может только суперпользователь, поэтому от его имени создаем файл touch.html cо следующим содержанием:

```

<html>
<body>test</body>
</html>

```

![Создание файла](image/8.png){#fig:008 width=70%}

Проверяю контекст созданного файла. По умолчанию — httpd_sys_content_t.

![Контекст файла](image/9.png){#fig:009 width=70%}

Обращаюсь к файлу через веб-сервер по адресу http://127.0.0.1/test.html. Файл отобразился успешно

![Отображение файла](image/10.png){#fig:010 width=70%}

Изучила справку man httpd_selinux.

![Изучение справки по команде](image/11.png){#fig:011 width=70%}

Проанализировала лог-файлы: tail -nl /var/log/messages

![Проверка лог-файлов](image/12.png){#fig:012 width=70%}

В файл error_log была записана информация.

![Проверка лог-файлов](image/13.png){#fig:013 width=70%}

Я выполняю команду semanage port -a -t http_port_t -p tcp 81. После этого я проверяю список портов командой semanage port -l | grep http_port_t. Порт 81 появился в списке.

![Проверка портов](image/14.png){#fig:014 width=70%}

Перезапускаю сервер Apache 

![Перезапуск сервера](image/15.png){#fig:015 width=70%}

Сервер работает, так как порт 81 добавлен в http_port_t. Возвращаю в /etc/httpd/httpd.conf порт 80. Проверяю — порт 81 удалён.

![Проверка порта 81](image/16.png){#fig:016 width=70%}

Далее удаляю файл test.html, проверяю, что он удален

![Удаление файла](image/17.png){#fig:017 width=70%}


# Выводы

В результате выполнения лабораторной работы я развила навыки администрирования Linux, получила первое практическое знакомство с SELinux и проверила его работу вместе с веб-сервером Apache.
