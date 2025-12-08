# 3) Конфигурирование сервера
##  1) Список параметров через запрос к представлению 'pg_settings' с условием context = 'postmaster'

В psql был выполнен запрос к представлению 'pg_settings':

```text
SELECT name, setting, context
FROM pg_settings
WHERE context = 'postmaster'
ORDER BY name;
```

Результат показывает параметры конфигурации, у которых context равен `postmaster`.

![](img/3.1.png) <br> Рисунок 3.1. Выполнение запроса к представлению 'pg_settings' и получение списка параметров конфигурации.

## 2) Ошибка в файле 'config/postgresql.conf'

В файле 'config/postgresql.conf' в блоке 'minimal baseline' допущена синтаксическая ошибка при изменении 'max_connections'.

![](img/3.2.png) <br> Рисунок 3.2. Синтаксическая ошибка в 'max_connections' в файле 'config/postgresql.conf'.
