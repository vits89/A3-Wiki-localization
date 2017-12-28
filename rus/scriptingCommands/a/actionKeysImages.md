# actionKeysImages

Игра: ArmA v1.0

## Описание

Возвращает список изображений кнопок или их названий назначенных для конкретного действия.

## Синтаксис #1

```SQF
actionKeysImages <действие>
```

Аргументы:

* <действие> STRING - имя действия. Можно найти в списке действий или в файле профиля (Вводить без префикса "key")

Результат:
STRUCTURED TEXT - список изображений кнопок или их названий

## Синтаксис #2

```SQF
actionKeysImages [<действие>, <макс. количесво>]
```

Аргументы:

* <действие> STRING - имя действия
* <макс. количесво> NUMBER - максимальное колличество клавиш или их комбинация в результате

Результат:
STRUCTURED TEXT - список изображений кнопок или их названий

## Пример(ы)

```SQF
actionKeysImages "MoveForward"; //'"W" or "UP"'
```

```SQF
actionKeysImages ["MoveForward", 1]; //'"W"'
```

## Дополнительная информация

* Имя действия можно найти в списке действий или в файле профиля (Вводить без префикса "key")
* Каждая клавиша в результате включена в двойные кавычки
* Разделяются клавишы в результате символами " or "
* Комбинации клавиш соединяются символом "+"
* При удержании клавиши добавляется надпись "Hold "
* При двойном нажатии клавиши добавляется надпись "2x"