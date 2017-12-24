# ARRAY
ARRAY - массив - это список элементов различных типов данных. Массивы могут быть как одномерными, так и многомерными.
## Создание (Определение)
Массив определеяется как список элементов между символами "[" и "]", разделенных символом ",". Массив может быть определен как пустым, так и уже содержащим определенные элементы. При обращении к элементу в массиве порядок индексации идет слева направо, начиная с 0 (0, 1, 2, ...):
```
//Пустой массив
myArray = [];
```
```
//Массив из 3 элементов типа STRING
myArray = ["Element0", "Element1", "Element2"];
```
Массивы передаются по ссылке, а не по значению, т. е. по адресу места где он хранится. Таким образом несколько переменных могут ссылаться на один и тот же массив. Если две переменные ссылаются на один и тот же массив, то некоторые действия с одной переменной будут влиять и на значение другой переменной:
```
//Две переменные ссылающиеся на один и тот же массив
myArray1 = ["Element0", "Element1", "Element2"];
myArray2 = myArray1;

//Операция с одной переменной
myArray1 pushBack "Element3"

//Т. к. переменные ссылаются на один и тот же массив, то результат будет следующим:
//myArray1 = ["Element0", "Element1", "Element2", "Element3"]
//myArray2 = ["Element0", "Element1", "Element2", "Element3"]
```
Начиная с ArmA 3 v1.55.133789 максимальное количество элементов в одном массиве ограничено 9999999 элементами.
## Многомерны массивы
Многомерными массивами являются массивы, которые содержат элементы типа ARRAY:
```
//Двумерный массив
myArray = [["Element00", "Element01", "Element02"], ["Element10", "Element11"]];
```
### select
Обращение к элементу в массиве выполняетс при помощи команды select:
```
myArray = ["Element0", "Element1", "Element2"];

myElement = myArray select 1;

//myElement = "Element1"
```
Эта команда также позволяет обратиться к элементу в многомерном массиве:
```
myArray = [["Element00", "Element01", "Element02"], ["Element10", "Element11"]];

myElement1 = myArray select 1;
myElement2 = myElement1 select 0;

//myElement1 = ["Element10", "Element11"]
//myElement2 = "Element10"
```
```
myArray = [["Element00", "Element01", "Element02"], ["Element10", "Element11"]];

myElement = (myArray select 1) select 0;

//myElement = "Element10"
```
При обращении к элементу массива, лежащему вне границ массива, с отрицательным индексом, скрипт прервет свое выполнение с ошибкой, а с положительным индексом вернет значение типа NOTHING:
```
myArray = ["Element0", "Element1", "Element2"];

myElement1 = myArray select 4;

//myElement1 = nil

myElement2 = myArray select -2;

//Скрипт прекратит свое выполнение с ошибкой: Error Zero Divisor
```
### set
Для определения значения элемента массива используется команда set:
```
myArray = ["Element0", "Element2", "Element2"];

myArray set [1, "Element1"];

//myArray = ["Element0", "Element1", "Element2"];
```
При задании элемента массива, лежащего вне границ массива, с отрицательным индексом, скрипт прервет свое выполнение с ошибкой, а с положительным индексом увеличит размерность массива командой resize так, что бы элемент с требуемым индексом был последним в массиве, промежуточные элементы заполняются значеием типа NOTHING, после чего выполняется присвоение значения:
```
myArray = ["Element0", "Element1", "Element2"];

myArray set [4, "Element4"];

//myArray = ["Element0", "Element1", "Element2", NULL, "Element4"]

myArray set [-2, "Element-2"];

//Скрипт прекратит свое выполнение с ошибкой: Error Zero Divisor
```
Для задания элемента в многомерном массиве, нужно использовать команду select:
```
myArray = [["Element00", "Element01", "Element02"], ["Element10", "Element12"]];

myElement = myArray select 1;
myElement set [1, "Element11"];

//myArray = [["Element00", "Element01", "Element02"], ["Element10", "Element11"]]
```
### count
Для определения числа элементов в массиве используется команда count:
```
myArray = ["Element0", "Element1", "Element2"];

myArrayCount = count myArray;

//myArrayCount = 3
```
Для определения числа элементов в многомерном массиве используется команда select:
```
myArray = [["Element00", "Element01", "Element02"], ["Element10", "Element11"]];

myArrayElement = myArray select 0;

myArrayCount1 = count myArray;
myArrayCount2 = count myArrayElement;

//myArrayCount1 = 2
//myArrayCount2 = 3
```
### pushBack
Для добавления элемента в конец массива используется команда pushBack:
```
myVariable = ["Element0", "Element1"];

myVariable pushBack "Element2";
//Сейчас myVariable имеет значение ["Element0", "Element1", "Element2"]
```
Такойже результат также можно получить через команду set:
```
myVariable = ["Element0", "Element1"];

myVariable set [count myVariable, "Element2"];
//Сейчас myVariable имеет значение ["Element0", "Element1", "Element2"]
```
### append
Для объединения массивом используется операция "+" или команда append:
```
myArray1 = ["Element0", "Element1"];
myArray1 = ["Element2", "Element3"];

myArray3 = myArray1 + myArray2;
myArray4 = myArray1 append myArray2;
//myArray3 = ["Element0", "Element1", "Element2", "Element3"]
//myArray4 = ["Element0", "Element1", "Element2", "Element3"]
//myArray3 и myArray4 содержат ссылки на разные массивы, и изменения в одной переменной не будут влиять на значение второй переменной
```
### Циклы
Удобным способом обращения к элементам массива являются конструкции for и forEach. for полезна когда нужно получить доступ к определенному списку элементов массива (Например, с 1 по 20 или каждый десятый), переменная-счетчик в данной конструкции будет выступать как индекс элемента массива, значение которого можно получить при помощи команды select. forEach выполняет код для каждого элемента массива, значение элемента может быть полученно из "магической" переменной _x, а индекс - _forEachIndex:
```
myArray = ["Element0", "Element1", "Element2"];

for "_i" from 0 to (count myVariable) - 1 do
{
    diag_log [_i, myArray select _i];
};
```
```
myArray = ["Element0", "Element1", "Element2"];

{
    diag_log [_forEachIndex, _x];
} forEach myArray;
```
### Копирование
Копирование массива может быть выполнено при помощи унарной операции "+". Она создает новый массив, являющийся копией предыдущего, и возвращает на него ссылку:
```
myArray1 = ["Element0", "Element2", "Element2"];
myArray2 = +myArray1;
myArray2 set [1, "Element1"];
//Сейчас myArray1 имеет значение ["Element0", "Element1", "Element2"];
//Сейчас myArray2 имеет значение ["Element0", "Element2", "Element2"];
```
Операция "+" копирует многомерный массив полностью, включая все подмассивы (Копирует не ссылку на него, а его элементы):
```
myArray1 = [["Element00", "Element02", "Element02"], ["Element10", "Element11"]];
myArray2 = +myArray1;

(myArray1 select 0) set [1, "Element01"];
//Сейчас myArray1 имеет значение [["Element00", "Element01", "Element02"], ["Element10", "Element11"]]
//Сейчас myArray2 имеет значение [["Element00", "Element02", "Element02"], ["Element10", "Element11"]]
```
### Удаление элементов
Для удаления элементов из массива используется бинарная операция "-" или команды deleteAt, deleteRange. Операция "-" удаляет все элементы из одного массива, который являются элементами второго массива:
```
myVariable1 = [1, "Element0", 2, "Element1", 3, "Element2"];
myVariable2 = [1, 2, "Element0"];

myVariable3 = myVariable1 - myVariable2;
//myVariable3 имеет значение ["Element1", 3, "Element2"];
```
deleteAt и deleteRange удаляют элементы из массива по их индексам:
```
myVariable = [1, "Element0", 2, "Element1", 3, "Element2"];

myVariable deleteAt 1;
//myVariable имеет значение [1, 2, "Element1", 3, "Element2"];

myVariable deleteRange [2, 3];
//myVariable имеет значение [1, 2];
```

### Удаление массива
Массив удаляет только тогда, когда не остается ни одной переменной содержащей ссылку на него:
```
myVariable1 = ["Element0", "Element2", "Element2"];
myVariable2 = myVariable1;
//Обе переменные ссылаются на один и тот же массив

myVariable1 = nil;
//Переменная myVariable1 уже не ссылается на массив, но т. к. переменная myVariable2 еще ссылается на него, то массив не удаляется, и может быть снова присвоен переменной myVariabl1

myVariable2 = ["Element0", "Element1", "Element2"];
//Переменная myVariable2 уже ссылается на новый массив, т. к. больше ни одна переменная не ссылается на старый массив, то он удаляется
```
### Округление индексов
Индекс элемента массива также может быть представлен в виде вещественного числа (Дробного), в таком случае индекс будет приведен к целому по следующим правилам:
* -0.5 <= i <= 0.5 будет округлен до 0
* 0.5 < i < 1.5 будет округлен до 1
* 1.5 <= i <= 2.5 будет округлен до 2
* 2.5 < i < 3.5 будет округлен до 3
* и т. д.