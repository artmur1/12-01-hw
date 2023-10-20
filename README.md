# Домашнее задание к занятию "`Базы данных`" - `Мурчин Артем`
---
### Легенда

Заказчик передал вам [файл в формате Excel](https://github.com/netology-code/sdb-homeworks/blob/main/resources/hw-12-1.xlsx), в котором сформирован отчёт. 

На основе этого отчёта нужно выполнить следующие задания.

### Задание 1

Опишите не менее семи таблиц, из которых состоит база данных:

- какие данные хранятся в этих таблицах;
- какой тип данных у столбцов в этих таблицах, если данные хранятся в PostgreSQL.

Приведите решение к следующему виду:

Сотрудники (

- идентификатор, первичный ключ, serial,
- фамилия varchar(50),
- ...
- идентификатор структурного подразделения, внешний ключ, integer).

### Решение 1

База данных состоит из следующих таблиц:

Таблица с ФИО сотрудников - хранятся фамилия, имя отчество сотрудника. Тип данных - строковый VARCHAR(50).

Таблица с окладами сотрудников - хранятся сумма оклада сотрудника. Тип данных - числовой DECIMAL/NUMERIC.

Таблица с должностями сотрудников - хранятся должность сотрудника. Тип данных - строковый VARCHAR(30).

Таблица с типами подразделений сотрудников - хранятся типы подразделений в которых работают сотрудники. Тип данных - строковый VARCHAR(50).

Таблица со структурными подразделениями сотрудников - хранятся структурные подразделения в которых работают сотрудники. Тип данных - строковый VARCHAR(50).

Таблица с датами найма сотрудников - хранятся даты наймов сотрудников. Тип данных - числовой MEDIUMINT

Таблица адрес филиала - хранятся адреса филиалов в которых работают сотрудники. Тип данных - строковый TEXT. Данную таблицу можно разделить на 3 таблицы: регион филиала, город филиала, улица и номер дома филиала.



![alt text](https://github.com/artmur1/12-01-hw/blob/main/12-01-murchin-1.png)

Провел нормализацию - создал 3 новых таблицы.

![alt text](https://github.com/artmur1/12-01-hw/blob/main/12-01-murchin-2.png)

Привел таблицу с сотрудниками к данному виду.

[Файл в формате Excel с нормализованной таблицей](https://github.com/artmur1/12-01-hw/blob/main/hw-12-1-murchin.xlsx).

### Доработка

Сотрудники (

идентификатор сотрудника, первичный ключ, serial,

ФИО сотрудника varchar(50),

Оклад DECIMAL/NUMERIC,

идентификатор должности, внешний ключ, integer,

идентификатор типа подразделения, внешний ключ, integer,

идентификатор структурного подразделения, внешний ключ, integer,

Дата найма MEDIUMINT,

идентификатор адреса филиала, внешний ключ, integer,

проект на который назначен varchar(50))

---

Должности (

идентификатор должности, первичный ключ, serial,

должность varchar(50))

---

Тип подразделения (

идентификатор типа подразделения, первичный ключ, serial,

тип подразделения VARCHAR(50))

---

Структурное подразделение (

идентификатор структурного подразделения, первичный ключ, serial,

структурное подразделение VARCHAR(50))

---

Адрес филиала (

идентификатор адреса филиала, первичный ключ, serial,

адрес филиала VARCHAR(100))


## Дополнительные задания (со звёздочкой*)
Эти задания дополнительные, то есть не обязательные к выполнению, и никак не повлияют на получение вами зачёта по этому домашнему заданию. Вы можете их выполнить, если хотите глубже шире разобраться в материале.


### Задание 2*

Перечислите, какие, на ваш взгляд, в этой денормализованной таблице встречаются функциональные зависимости и какие правила вывода нужно применить, чтобы нормализовать данные.
