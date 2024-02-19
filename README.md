# Домашнее задание к занятию 6. «Troubleshooting» - Филатов А. В.

## Задача 1

Перед выполнением задания ознакомьтесь с документацией по [администрированию MongoDB](https://docs.mongodb.com/manual/administration/).

Пользователь (разработчик) написал в канал поддержки, что у него уже 3 минуты происходит CRUD-операция в MongoDB и её 
нужно прервать. 

Вы как инженер поддержки решили произвести эту операцию:

- напишите список операций, которые вы будете производить для остановки запроса пользователя;
- предложите вариант решения проблемы с долгими (зависающими) запросами в MongoDB.

## Решение 1

### Операции для остановки запроса пользователя:
1. Получение информации о текущих операциях:
  - Используя команду db.currentOp() в MongoDB Shell, можно получить список текущих операций и их статус.

2. Определение ID операции:
  * Из выдачи db.currentOp() определите ID операции, соответствующей запросу пользователя.

3. Прерывание операции:
  * Используя команду db.killOp(<opid>), где <opid> - ID операции, можно прервать выполнение конкретной операции.

# Решение проблемы с долгими запросами:
1. Индексация:
  * Убедитесь, что используются необходимые индексы для ускорения операций.

2. Оптимизация запросов:
  * Проверьте запрос пользователя на возможность оптимизации. Используйте explain() для анализа выполнения запроса.

3. Анализ журналов:
  * Просмотрите журналы MongoDB (mongod.log) для выявления проблем и предупреждений.

4. Настройка профилирования:
  * Включите профилирование для отслеживания долгих операций и анализа запросов.

## Задача 2

Перед выполнением задания познакомьтесь с документацией по [Redis latency troobleshooting](https://redis.io/topics/latency).

Вы запустили инстанс Redis для использования совместно с сервисом, который использует механизм TTL. 
Причём отношение количества записанных key-value-значений к количеству истёкших значений есть величина постоянная и
увеличивается пропорционально количеству реплик сервиса. 

При масштабировании сервиса до N реплик вы увидели, что:

- сначала происходит рост отношения записанных значений к истекшим,
- Redis блокирует операции записи.

Как вы думаете, в чём может быть проблема?

## Решение 2

 
## Задача 3

Вы подняли базу данных MySQL для использования в гис-системе. При росте количества записей в таблицах базы
пользователи начали жаловаться на ошибки вида:
```python
InterfaceError: (InterfaceError) 2013: Lost connection to MySQL server during query u'SELECT..... '
```

Как вы думаете, почему это начало происходить и как локализовать проблему?

Какие пути решения этой проблемы вы можете предложить?

## Решение 3


## Задача 4


Вы решили перевести гис-систему из задачи 3 на PostgreSQL, так как прочитали в документации, что эта СУБД работает с 
большим объёмом данных лучше, чем MySQL.

После запуска пользователи начали жаловаться, что СУБД время от времени становится недоступной. В dmesg вы видите, что:

`postmaster invoked oom-killer`

Как вы думаете, что происходит?

Как бы вы решили эту проблему?

## Решение 4


---

### Как cдавать задание

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---
