---
title: "pr2"
format: html
editor: visual
---

## Цель

Проанализировать сетевой трафик устройства и определить процент трафика, явлюющегося нежелательным

## Исходные данные

1.  Ноутбук с Parrot OS
2.  Редактор VS Code
3.  Python 3.7
4.  Wireshark
5.  Zeek

##Вариант решения

1.  Wireshark захватывает сетевой трафик
2.  Zeek выделяет метаданные трафика
3.  Программа определяет процент нежелательного трафика

## План

1.  Собрать трафик
2.  Выделить метаднные в .log файл
3.  Написать программу
4.  Провести анализ трафика

## Описание шагов

1.  Сбор трафика

<img width="614" alt="image" src="https://user-images.githubusercontent.com/87472380/230713778-8b37c3e4-9ef1-4b69-8b2c-d23e70744ab1.png">

2.  Выделение метаданных с помощью утилиты zeek

Сохраним захваченных трафик, воспользуемся следующей командой:

```{bash}
/opt/zeek/bin/zeek -C -r /home/heis3nberg/Downloads/traf.pcanpg
```

В результате метаданные будут сохранены в файл /opt/zeek/bin/dns.log
<img width="964" alt="image" src="https://user-images.githubusercontent.com/87472380/230713713-f6abd075-f311-4b99-a92e-9ea874cb48c3.png">

3.  Напишем программу на языке python для анализа логов на нежелательный трафик, в качестве побочного средства будем использовать файл hosts.txt (https://github.com/StevenBlack/hosts/blob/master/data/add.2o7Net/hosts), содержащий список нежелательных доменных имен

```{python}
import re
with open('res.txt') as f:
    i = 0
    for count, line in enumerate(f):
        pass

countBad = 0

f = open('res.txt')
h = open('hosts.txt')
br = h.read()
i = 0
for line in f:
    i+=1
    if(i<=7):
        continue
    if i == count+1 :
        break

    temp = line.split()
    if str(temp[9]) in br:
        countBad += 1
print(str(round(countBad * 100/ (count-7), 2)) + '%')

```

4.  В результате получаем: 18.2% от всего трафика является нежелательным
<img width="223" alt="image" src="https://user-images.githubusercontent.com/87472380/230713684-57947aaa-ee5c-4c71-8338-f0e6361a3e95.png">


## Оценка результатов

Задача решена с помощью python, zeek и wireshark. Я научился захватывать трафик в реальном времени и анализировать его.

## Вывод

В данной работе я провел анализ своего трафика в сети и выявил, что практически одна пятая его часть является нежелательной и, возможно, скрытой от меня. Берегите себя и своих близких, пользуйтесь AdBlock и относитесь ответственно к интернет-серфингу.
