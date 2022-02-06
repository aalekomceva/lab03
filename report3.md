---
# Front matter
lang: ru-RU
title: 'Отчёт'
subtitle: 'по лабораторной работе 3'
author: 'Лекомцева Алёна'

# Formatting
toc-title: 'Содержание'
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 11pt
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

Получение практических навыков работы в консоли с атрибутами файлов для групп пользователей.

# Задание

Лабораторная работа подразумевает дискреционное разграничение прав в Linux. Два пользователя

# Выполнение лабораторной работы

1. Пользователь guest создан в предыдущей лабораторной работе.

2. Аналогично создаем второго пользователя guest2 (рис.1).

   ![рис.1. Создание guest2.](images/1.jpg){ #fig:001 width=60% }

3. Добавляем пользователя guest2 в группу guest. (рис.2).

   ![рис.2. Добавление guest2 в группу guest.](images/2.jpg){ #fig:002 width=60% }

4. Осуществляем вход в систему от двух пользователей на двух разных консолях: guest на первой консоли и guest2 на второй консоли.
Для обоих пользователей командой pwd определяем директорию, в которой мы находимся. Также командой _id_ уточняем имя пользователя, его группу, кто входит в неё и к каким группам принадлежит он сам. Для пользователя guest - uid = 1001, gid = 1001, состоит в группе 1001 (guest); а для guest2 - uid = 1002, gid = 1002, состоит в группах guest2 и guest - то есть в группах с id 1002 и 1001.
Также определить в какие группы входят пользователи guest и guest2 можно командами _groups guest_ и _groups guest2_ соответственно. А команды _id -G_ и _id -Gn_ выводят идентификаторы и имена групп, в которые входят пользователи. 
Как видим вывод команд  _groups_ и _id -Gn_ одинаковы, в отличии от команды _id -G_, которая выводит числовой идентификатор. (рис.3-4)

   ![рис.3. Информация о пользователе guest.](images/3.jpg){ #fig:003 width=60% }

   ![рис.4. Информация о пользователе guest2.](images/4.jpg){ #fig:004 width=60% }

5. Сравниваем полученную информацию с содержимым файла /etc/group. Просматриваем файл командой _cat /etc/group_, которая показывает id группы пользователя и тех, кто входит в нее. (рис.5).

   ![рис.5. Команда cat.](images/5.jpg){ #fig:005 width=60% }

6. От имени пользователя guest2 выполним регистрацию пользователя guest2 в группе guest. (рис.6).

   ![рис.6. Регистрация guest2 в группе guest.](images/6.jpg){ #fig:006 width=60% }
   
7. Воспользовавшись командой _chmod g+rwx /home/guest_, от имени пользователя guest изменим права директории /home/guest, разрешив все действия для пользователей группы. А затем снимим с директории /home/guest/dir1 все атрибуты командой _chmod 000 dirl_. И проверим правильность снятия атрибутов командой _ls -l_. (рис.7)

   ![рис.7. Изменение прав директории.](images/7.jpg){ #fig:007 width=60% }

8. Заполним таблицу «Установленные права и разрешённые действия для групп», последовательно меняя права доступа для директории и файла от имени пользователя guest и проверяя разрешенные действия для пользователя guest2. (рис.8, табл.1)

   ![рис.8. Проверка разрешенных действий для групп.](images/8.jpg){ #fig:008 width=60% }

   ![табл.1. «Установленные права и разрешённые действия для групп».](images/9.jpg){ #fig:009 width=60% }
  
9. Минимальные права для совершения операций от имени пользователей входящих в группу. (табл.2)

   ![табл.2. «Минимальные права для совершения операций для пользователей группы».](images/10.jpg){ #fig:010 width=60% }




# Выводы

В ходе выполнения работы я приобрела практические навыки работы в консоли с атрибутами файлов для групп пользователей.
