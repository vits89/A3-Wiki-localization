# TASK
TASK или ЗАДАНИЕ - это тип данных, который сожержит ссылку на задание (Также известная как "задача"). Задание имеет описание, точку назначения и статус, отображается в брифинге в разделе "задачи". Задание привязано к юниту.
```
myTask = player createSimpleTask ["myTask"];
myTask setSimpleTaskDescription ["Remove enemy", "Clear enemy", "Danger"];
myTask setSimpleTaskDestination (getMarkerPos "myTaskMarker");
myTask setTaskState "Created";
```
Задание может иметь один из следующих статусов:
* "Succeeded" - выполнено
* "Failed" - провалено
* "Canceled" - отменено
* "Created" - создано, новое
* "Current" - текущее, назначено