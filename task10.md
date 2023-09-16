__Проверка деления на 0:__

1) было:
```
ratioMaxSalaryToMin = zp_max / zp_min;
```
стало:
```
ratio = 0;
if(zp_min != 0) {
  ratio = zp_max / zp_min;
}
```
2) при вычислении времени добавлена проверка на нулевую скорость:
```
time_h = 0;
if(velocity_kmh != 0) {
  time_h = distance_km / velocity_kmh;
}
```
__Избавление от магических символов и строк:__

3) было:
```
boolean shouldIncluded = arrayRoundLength[i] != '0' && arrayRoundLength[i] != ',';
```
стало:
```
INVALID_CHAR = '0';
SEPARATOR_COMMA = ',';
...
boolean shouldIncluded = arrayRoundLength[i] != INVALID_CHAR && arrayRoundLength[i] != SEPARATOR_COMMA;
```
4) было:
```
if(text[i] != ' ') { ... }
```
стало:
```
SEPARATOR_SPACE = ' ';
...
if(text[i] != SEPARATOR_SPACE) { ... }
```
5) вынесла шрифт при работе с графикой в константы:
```
FONT_OF_TEXT = "Arial";
```
6) аналогично вынесла магическую строку:
```
IMAGE_EXTENSION = " jpg";
```
__Использование логических переменных для повышения читабельности программы:__

7) было:
```
if(checkDif == 1 || checkSum == 7 || checkSum == 10) { ... }
```
стало:
```
boolean scrolledHorizOrVert = checkDif == 1 || checkSum == 7 || checkSum == 10;
if(scrolledHorizOrVert) { ... }
```
8) было:
```
if(arrayRoundLength[i] != '0' && arrayRoundLength[i] != ',') { ... }
```
стало:
```
boolean shouldIncluded = arrayRoundLength[i] != '0' && arrayRoundLength[i] != ',';
if(shouldIncluded) { ... }
```
9) было:
```
if(countOfSymb.get(i) == countOfSymb.get(i - 1)) { ... }
```
стало:
```
boolean isEqualFrequency = countOfSymb.get(i) == countOfSymb.get(i - 1);
if(isEqualFrequency) { ... }
```
10) было:
```
if((countOfSymb.get(i) - 1 == countOfSymb.get(i - 1) || countOfSymb.get(i) == countOfSymb.get(i - 1) - 1) && countDel == 0) { ... }
```
стало:
```
boolean isEqualWhenDelOneChar = countOfSymb.get(i) - 1 == countOfSymb.get(i - 1) || countOfSymb.get(i) == countOfSymb.get(i - 1) - 1;
if(isEqualWhenDelOneChar && countDel == 0) { ... }
```
__Проверка на переполнение:__

11) при вычислении факториала добавлена проверка на переполнение сверху:
```
for(int i = 1; i <= N; i++) {
    if(factorial * i < 0) {
        throw new UnsupportedOperationException("Overflow from above");
    }
    factorial *= i;
}
```
12) аналогично в калькуляторе добавлена проверка на переполнение сверху/снизу.
