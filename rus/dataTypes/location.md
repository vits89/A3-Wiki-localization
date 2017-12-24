# LOCATION
Локация - это расширенный тип маркера, появившийся в ArmA 1.08. Локация отличается от маркера следующими свойствами:
* Локация имеет название, стороны, 3D-коориданты, 2D-зону и ориентацию
* Локация отображаются на карте без масштабирования
* Локация требует определения класса в configFile >> "CfgLocationTypes" для определения базовых свойств, который могут быть изменены скриптами.
* Локация может быть закреплена за объектом
* Локация является пространством имен и к ней может быть применены команды setVariable и getVariable
* Локация всегда локальна для каждого клиента в сетевой игре и их свойства не синхронизируются
* Локации для карты устанавливаются в .pew файле
* Локации карты могут быть найдены скриптовыми командами, но не могут быть изменены. Это позволяет находить ближайшие вершины, города и т. д.
## Типы локаций
### Armed Assault
* Mount
* Name
* NameMarine
* NameCityCapital
* NameCity
* NameVillage
* NameLocal
* Hill
* ViewPoint
* RockArea
* BorderCrossing
* VegetationBroadleaf
* VegetationFir
* VegetationPalm
* VegetationVineyard
### ArmA 2
* Name
* Strategic
* StringpointArea
* FlatArea
* FlatAreaCity
* FlatAreaCitySmall
* CityCenter
* Airport
* NameMarine
* NameCityCapital
* NameCity
* NameVillage
* NameLocal
* Hill
* ViewPoint
* RockArea
* BorderCrossing
* VegetationBroadleaf
* VegetationFir
* VegetationPalm
* VegetationVineyard
### ArmA 3
* NameCity
* NameCityCapital
* NameMarine
* NameVillage
* NameLocal
* Hill
* Mount
* Airport