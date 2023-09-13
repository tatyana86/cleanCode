3.1.  
Для решения задачи теплопроводности необходимо задать одно из трех типов граничных условий (г. у.):  
1) г.у. первого рода - задается температура на границе тела:
```
ThermalConductivity compressorBlade = ThermalConductivity.firstBoundaryCondition(double temperature);
```
2) г.у. второго рода - задается тепловой поток:
```
ThermalConductivity turbineBlade = ThermalConductivity.secondBoundaryCondition(double heatFlow);
```
3) г.у. третьего рода - задается коэффициент конвективной теплоотдачи и температура охладителя:
```
ThermalConductivity compressorDisk = ThermalConductivity.thirdBoundaryCondition(double heatConvCoef, double temperatureOfCool);
```
3.2.
Абстрактный класс должен иметь как можно общное название, которое будет отражать все наследованные классы, например:
- Animal (наследованные Bird, Fish, Mammal и т.д.);
- Human (наследованные Man, Woman).
