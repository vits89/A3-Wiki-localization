# addBackpackCargoGlobal

Игра: ArmA 2 OA v1.55
Аргументы: глобальные
Эффект: глобальный

## Описание

Добавляет рюкзак(и) в грузовой отсек машины. MP-синхронизированная.

## Синтаксис

```SQF
<машина> addBackpackCargoGlobal [<рюкзак>, <количество>]
```

Аргументы:

* <машина> OBJECT - машина, в которую нужно добавить рюкзак
* <рюкзак> STRING - название класса рюкзака
* <количество> NUMBER - количество рюкзаков

Результат:
NOTHING

## Пример(ы)

```SQF
this addBackpackCargoGlobal ["TK_RPG_Backpack_EP1", 2];
```

```SQF
_apc addBackpackCargoGlobal ["US_Patrol_Pack_EP1", 4];
```

## Дополнительная информация

* Название класса рюкзака можно найти в списке объектов или в файле конфигурации (начинаются с "B_"):

```SQF
"CfgVehicles"
```
