# add3DENEventHandler

Игра: ArmA 3 v1.56

## Описание

Добавляет обработчик события редактора 3DEN

## Синтаксис

```SQF
add3DENEventHandler [<событие>, <скрипт>]
```

Аргументы:

* <событие> STRING - имя события редактора 3DEN
* <скрипт> CODE - обработчик события

Результат:
NUMBER - идентификатор обработчика события

## Пример(ы)

```SQF
add3DENEventHandler ["onUndo", {systemChat str _this}];
```

## Дополнительная информация

Нет