# actionKeys

Игра: ArmA v1.0

## Описание

Возвращает массив, содержащий коды клавиш и комбинаций клавиш, назначеных для конкретного действия.

## Синтаксис

```SQF
actionKeys <действие>
```

Аргументы:

* <действие> STRING - имя действия. Можно найти в списке действий или в файле профиля (Вводить без префикса "key")

Результат:
ARRAY из NUMBERs - массив кодов назначеных клавиш и комбинаций клавиш

## Пример(ы)

```SQF
actionKeys  "MoveForward";  //[17,200]
```

## Дополнительная информация

* Если клавиша назначена как комбинация клавиш (Например, Ctrl + M) невозмодно однозначно определить т. к. их реальное значение находится за границами представления чисел в скриптах