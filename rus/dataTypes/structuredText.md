# STRUCTURED TEXT
STRUCTURED TEXT или СТРУКТУРИРОВАННЫЙ ТЕКСТ - это тип данныех, который хранит текст, который может содержать изображения и форматирование.
## Атрибуты
### size
Множитель размера шрифта:
```
"<t size='2'>Текста в 2 раза больше</t>";
"<t size='0.5'>Текста в 2 раза меньше</t>";
```
### align
Горизонтальное выравнивание текста:
```
"<t align='left'>Текст слева</t>";
"<t align='center'>Текст по центру</t>";
"<t align='right'>Текст справа</t>";
```
### valign
Вертикальное выравнивание текста:
```
```
### color
Цвет текста:
```
"<t color='#FF0000'>Красный текст</t>";
"<t color='#7F00FF00'>Прозрачный зеленый текст</t>";
```
Доступные форматы цвета:
* RGB - красный, зеленый, синий
* ARGB - прозрачность, красный, зеленый, синий
### font
Шрифт:
```
"<t font='LucidaConsoleB'>Текст моноширинным шрифтом</t>";
```
Доступные шрифты (ArmA 3):
* EtelkaMonospacePro
* EtelkaMonospaceProBold
* EtelkaNarrowMediumPro
* LCD14
* LucidaConsoleB
* PuristaBold
* PuristaLight
* PuristaMedium
* PuristaSemibold
* RobotoCondensed
* RobotoCondensedBold
* RobotoCondensedLight
* TahomaB
### image
Изображение:
```
"<img image='\A3\ui_f\data\map\markers\nato\b_inf.paa' />";
```
### shadow
Тень от текста:
```
"<t shadow='1'>Класическая тень</t>";
"<t shadow='2'>Тень по контуру</t>";
```
Типы теней:
* 0 - нет тени
* 1 - класическая тень
* 2 - тень по контуру
### shadowOffset
Смещение тени от текста:
```
```
### shadowColor
Цвет тени от текста:
```
"<t shadow='1' shadowColor='#ff0000>Текст с класической красной тенью</t>";
```
Доступные форматы цвета:
* RGB - красный, зеленый, синий
* ARGB - прозрачность, красный, зеленый, синий
Тень по контуру всегда черная, её цвет изменить нельзя
### underline
Подчеркивание текста:
```
"<t underline='true'>Подчеркнутый текст</t>"
```
Обычный пробел разделяет линию подчеркивание, что бы избежать этого нужно заменить пробел неразрывным пробелом (0xA0):
```
format ["<t underline='true'>Подчеркнутый%1текст%1с%1неразрвными%1пробелами</t>", toString [0xA0]];
```
### href
Ссылка:
```
"<a href='https://google.com'>Ссылка на google.com</a>";
```
Изображение с ссылкой:
```
"<a href='https://google.com'><img image='\A3\ui_f\data\map\markers\nato\b_inf.paa' /></a>";
```
### colorLink
Цвет текста в ссылке:
```
"<t colorLink='#ffff00"><a href='https://google.com'>Желтая ссылка на google.com</a></t>;
```