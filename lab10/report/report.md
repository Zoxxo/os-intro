---
# Front matter
lang: ru-RU
title: "Лабораторная работа № 10."

author: "Кальсин Захар Алексеевич"

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

  Познакомиться с операционной системой Linux, получить практические навыки работы с редактором Emacs. 
# Выполнение лабораторной работы

1.Открыл emacs.
![](image/r.png){ #fig:001 width=70% }
2.Создал файл lab07.sh с помощью комбинации Ctrl-x Ctrl-f (C-x C-f).
![](image/0.png){ #fig:001 width=70% }
3.Набрал текст:
![](image/00.png){ #fig:001 width=70% }
#!/bin/bash

HELL=Hello

function hello {

LOCAL HELLO=World

echo $HELLO

}

echo $HELLO

hello

4. Сохранил файл с помощью комбинации Ctrl-x Ctrl-s (C-x C-s).
![](image/000.png){ #fig:001 width=70% }
5. Проделаk с текстом стандартные процедуры редактирования, каждое действие осуществлялось комбинацией клавиш.

5.1. Вырезал одной командой целую строку (С-k).
![](image/0000.png){ #fig:001 width=70% }
5.2. Вставил эту строку в конец файла (C-y).
![](image/00000.png){ #fig:001 width=70% }
5.3. Выделил область текста (C-space).
![](image/000000.png){ #fig:001 width=70% }
5.4. Скопировал область в буфер обмена (M-w).

5.5. Вставил область в конец файла.
![](image/0000000.png){ #fig:001 width=70% }
5.6. Вновь выделил эту область и на этот раз вырезал её (C-w).
![](image/00000000.png){ #fig:001 width=70% }
5.7. Отменил последнее действие (C-/).
![](image/000000000.png){ #fig:001 width=70% }
6. Научилась использовать команды по перемещению курсора.

6.1. Переместил курсор в начало строки (C-a).

6.2. Переместил курсор в конец строки (C-e).

6.3. Переместил курсор в начало буфера (M-<).

6.4. Переместил курсор в конец буфера (M->).

7. Управление буферами.

7.1. Вывел список активных буферов на экран (C-x C-b).
![](image/0000000000.png){ #fig:001 width=70% }
7.2. Переместилась во вновь открытое окно (C-x) o со списком открытых буферов и переключилась на другой буфер.
![](image/1.png){ #fig:001 width=70% }
7.3. Закрыл это окно (C-x 0).
![](image/2.png){ #fig:001 width=70% }
7.4. Вновь переключился между буферами, но без вывода их списка на экран (C-x b).
![](image/3.png){ #fig:001 width=70% }
8. Управление окнами.

8.1. Поделил фрейм на 4 части: разделила фрейм на два окна по вертикали
![](image/4.png){ #fig:001 width=70% }
(C-x 3), а затем каждое из этих окон на две части по горизонтали (C-x 2).

8.2. В каждом из четырёх созданных окон открыл новый буфер (файл) и ввела несколько строк текста.

9. Режим поиска

9.1. Переключился в режим поиска (C-s) и нашла несколько слов, присутствующих в тексте.
![](image/5.png){ #fig:001 width=70% }
9.2. Переключался между результатами поиска, нажимая C-s.
![](image/6.png){ #fig:001 width=70% }
9.3. Вышол из режима поиска, нажав C-g.

9.4. Перешол в режим поиска и замены (M-%), ввел текст, который следует найти и заменить, нажала Enter , затем ввел текст для замены. После того как были подсвечены результаты поиска, нажал ! для подтверждения замены.
![](image/7.png){ #fig:001 width=70% }
9.5. Испробовал другой режим поиска, нажав M-s o. Он отличается от обычного режима тем, что при поиске указывает номера строк в которых найдено введённое слово и выделяет их цветом. В обычном режиме выделение цветом появляется, только когда нужно подтвердить замену.

Вывод: познакомился с операционной системой Linux, получил практические навыки работы с редактором Emacs.

Ответы на контрольные вопросы:

1. Emacs представляет собой мощный экранный редактор текста, написанный на

языке высокого уровня Elisp.

2. Развитие Emacs в сторону его многогранности послужило причиной того, что и без

того интуитивно непонятная программа стала чрезвычайно сложной в применении. В частности, управление осуществляется при помощи различных клавиатурных комбинаций, запомнить которые будет непросто.

3. Буфер – что-то, состоящее из текста.

Окно – область с одним из буферов.

4. В одном окне можно открыть больше 10 буферов.

5. После запуска emacs без каких-либо параметров в основном окне отображается буфер *scratch*, который используется для оценки выражений Emacs Lisp, а также для заметок, которые вы не хотите сохранять. Этот буфер не сохраняется автоматически.

6. Чтобы ввести следующую комбинацию C-c | я нажму клавиши: Control+c и Shift+\, и для C-c C-|: Control+c и Control+Shift+\.

7. Поделить текущее окно на две части можно двумя комбинациями клавиш:

C-x 3 или C-x 2.

8. Настроить или расширить Emacs можно написав или изменив файл ~/.emacs.

9. Клавиша ß выполняет функцию перемещения курсора в открытом окне также, как и многие другие клавиши её можно переназначить.

10. Редактор emacs показался мне удобнее из-за возможности открытия нескольких окон с буферами и работать комбинациями клавиш в этот редакторе мне было проще