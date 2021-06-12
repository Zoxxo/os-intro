---
## Front matter
lang: ru-RU
title: Лабораторная работа № 15.
author: "Кальсин З. А."
institute: 
	\inst{1}RUDN University, Moscow, Russian Federation

date: 
## Formatting
toc: false
slide_level: 2
theme: metropolis
header-includes: 
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'
aspectratio: 43
section-titles: true
---

# Цель работы

     приобретение практических навыков работы с именованными каналами 
# Выполнение лабораторной работы

Ход работы:

1.Изучил приведённые в тексте программы server.c и client.c и взял данные

примеры за образец.

common.h:
![](image/1.png){ #fig:001 width=70% }

## Слайд 1

server.c:
![](image/2.png){ #fig:001 width=70% }

## Слайд 2

![](image/2.1.png){ #fig:001 width=70% }

## Слайд 3

client.c:
![](image/3.png){ #fig:001 width=70% }

## Слайд 4

2.Написал аналогичные программы, внеся следующие изменения:

- работает не 1 клиент, а несколько (например, два).

- клиенты передают текущее время с некоторой периодичностью (например, раз

в пять секунд). Использовала функцию sleep() для приостановки работы клиента.

- сервер работает не бесконечно, а прекращает работу через некоторое время (например, 30 сек). Использовала функцию clock() для определения времени работы

сервера.

## Слайд 5

common.h:
![](image/1.png){ #fig:001 width=70% }

## Слайд 6

server.c:
![](image/2.png){ #fig:001 width=70% }

## Слайд 7

![](image/2.1.png){ #fig:001 width=70% }


## Слайд 8

client.c:
![](image/.png){ #fig:001 width=70% }

## Слайд 9

client2.c:
![](image/3.png){ #fig:001 width=70% }

## Слайд 10

![](image/4.png){ #fig:001 width=70% }

## Слайд 11

![](image/5.png){ #fig:001 width=70% }

## Слайд 12

В случае, если сервер завершит работу, не закрыв канал, файл FIFO не удалится, поэтому его в следующий раз создать будет нельзя и вылезет ошибка, следовательно, работать ничего не будет.


## Слайд 13

# Вывод: приобрел практические навыки работы с именованными каналами.

Ответы на контрольные вопросы:

# Ответы на контрольные вопросы:

1.Именованные каналы отличаются от неименованных наличием идентификатора

канала, который представлен как специальный файл (соответственно имя именованного канала — это имя файла). Поскольку файл находится на локальной файловой системе, данное IPC используется внутри одной системы.

2.Создание неименованного канала из командной строки невозможно.

3.Создание именованного канала из командной строки возможно.

## Слайд 14

4. int read(int pipe_fd, void *area, int cnt);

int write(int pipe_fd, void *area, int cnt);

Первый аргумент этих вызовов - дескриптор канала, второй - указатель на область памяти, с которой происходит обмен, третий - количество байт. Оба вызова возвращают число переданных байт (или -1 - при ошибке).

5. int mkfifo (const char *pathname, mode_t mode) ;

mkfifo(FIFO_NAME, 0600) ;

Первый параметр — имя файла, идентифицирующего канал, второй параметр маска прав доступа к файлу. Вызов функции mkfifo() создаёт файл канала (с именем, заданным макросом FIFO_NAME).


## Слайд 15

6. При чтении меньшего числа байтов, чем находится в канале, возвращается требуемое число байтов, остаток сохраняется для последующих чтений. При чтении большего числа байтов, чем находится в канале или FIFO возвращается доступное число байтов.

7. При записи большего числа байтов, чем это позволяет канал или FIFO, вызов write(2) блокируется до освобождения требуемого места. При этом атомарность операции не гарантируется. Если процесс пытается записать данные в канал, не открытый ни одним процессом на чтение, процессу генерируется сигнал. Запись числа байтов, меньшего емкости канала или FIFO, гарантированно атомарно. Это означает, что в случае, когда несколько процессов одновременно записывают в канал, порции данных от этих процессов не перемешиваются.

8. В общем случае возможна много направленная работа процессов с каналом, т.е. возможна ситуация, когда с одним и тем же каналом взаимодействуют два и более процесса, и каждый из взаимодействующих каналов пишет и читает информацию в канал. Но традиционной схемой организации работы с каналом является однонаправленная организация, когда канал связывает два, в большинстве случаев, или несколько взаимодействующих процесса, каждый из которых может либо читать,
либо писать в канал.

## Слайд 16

9. Write - Функция записывает length байтов из буфера buffer в файл, определенный дескриптором файла fd. Эта операция чисто 'двоичная' и без буферизации. Реализуется как непосредственный вызов DOS. С помощью функции write мы посылаем сообщение клиенту или серверу.

10. Строковая функция strerror - функция языков C/C++, транслирующая код ошибки, который обычно хранится в глобальной переменной errno, в сообщение об ошибке, понятном человеку. Ошибки эти возникают при вызове функций стандартных Си-библиотек. Возвращенный указатель ссылается на статическую строку с ошибкой, которая не должна быть изменена программой. Дальнейшие вызовы функции strerror перезапишут содержание этой строки. Интерпретированные сообщения об ошибках могут различаться, это зависит от платформы и компилятора.