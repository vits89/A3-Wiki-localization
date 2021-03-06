# addAction

Игра: OFP v1.1
Аргументы: глобальные
Эффект: локальный

## Описание

Добавляет действие к объекту, которое показывается в списке действий (При вращении колесика мышки)

## Синтаксис

```SQF
<объект> addAction [<заголовок>, <скрипт>, (<аргументы>, <приоритет>, <показ. иконку>, <закрывать меню после использования>, <действие>, <условие>, <радиус>, <без сознания>, <выборка>)]
```

Аргументы:

* <объект> OBJECT - объект, к которому будет добавлено действие
* <заголовок> STRING - имя действия, которое будет отображаться в списке действий
* <скрипт> - код, который будет вызван при выполнении действия:
  * STRING - путь к файлу со скриптом (Строка должна содержать расширение .sqf или .sqs) или обычный код в строке
  * CODE - скомпилированный код
* <аргументы> ANYTHING - аргументы, которые будут переданы в скрипт действия (По умолчанию: nil)
* <приоритет> NUMBER - приоритет действия. Чем больше приоритет у действия, тем выше оно будет в списке действий. Действия с одинаковым приоритетом сортируются в порядке их создания - старые выше, новые ниже (По умолчанию: 1.5)
* <показ. иконку> BOOL - если true, то игрок увидит имя действия в центре экрана при наведении на объект. Для отображения действия данным способом оно должно иметь приоритет выше, чем любые другие доступные в данный момент действия для данного объекта (По умолчанию: false)
* <закрывать меню после использования> BOOL - если true, то при нажатии игроком на это действие список действий будет закрыт, иначе продолжит показываться, пока игрок его не закроет сам или не выполнит другое действие (По умолчанию: true)
* <действие> STRING - имя действия, на которое будет назначено данное действие как быстрая комбинация для вызова (По умолчанию: "")
* <условие> STRING - код-условие для появления действия (По умолчанию: "true")
* <радиус> NUMBER - радиус в метрах, в котором юнит может активировать данное действие (По умолчанию: 15)
* <без сознания> BOOL - если true, то игрок может выполнить данное действие в без сознательном состоянии (По умолчанию: false)
* <выборка> STRING - название точки в геометрическом LOD'е объекта, к которой будет прикреплено данное действие (По умолчанию: "")

Результат:
NUMBER - идентификатор действия

## Пример(ы)

```SQF
player addAction ["Бесполезное действие", {}];
```

```SQF
player addAction ["<t color='#FF0000'>Бесполезное действие красным текстом</t>", {}];
```

```SQF
player addAction ["Hello World!", {hint format ["Hello %1!", _this select 3]}, name player];
```

```SQF
player addAction ["Вызвать файл", "myScript.sqf"];
```

## Дополнительная информация

* Аргумент <аргументы> доступен в скрипте по следующему коду:

```SQF
_this select 3;
```

* Имя действия можно найти в списке действий или в файле профиля (Вводить без префикса "key")
* Максимальный радиус равен 15 метрам
* Данная команда будет проигнорирована на выделеном сервере и безголовом клиенте т. к. у них отсутствует интерфейс
* Данная команда не работает на животных