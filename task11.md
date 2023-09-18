__Инициализация всех без исключений атрибутов/полей класса в его конструкторе:__

1) было:
```
Dwarf(String n, int a)
{
  this.nameOfDwarf = n;
  this.ageOfDwarf = a;
  this.lengthOfBeard = 0;
}
```
стало:
```
Dwarf(String n, int a)
{
  this.nameOfDwarf = n;
  this.ageOfDwarf = a;
  this.lengthOfBeard = 0;
  this.currentActivity = "no job";
  this.religionOfDwarf = "dubious";
  this.isMarried = false;
}
```
__Объявление переменных-хранилищ с помощью final:__

2)
```
final int RADIX_EIGHT = 8;
final int RADIX_SIXTEEN = 16;
```
3)
```
final int PI_NUMBER = 3.1416;
final int E_NUMBER = 2.7183;
final int NORMAL_ATMOSPHERIC_PRESSURE_PA = 101325;
```
4)
```
final int CAPITAL_A_ASCII = 65;
final int SMALL_A_ASCII = 97;
```

__Инициализация переменных непосредственно перед их использованием:__

5) было:
```
String result = "";
// много кода
char [] arrayRoundLength = roundLength.toCharArray();
for(int i = 0; i < arrayRoundLength.length; i ++) {
    if(shouldIncluded) {
        result += arrayRoundLength[i];
    }
}
```
стало:
```
// много кода
char [] arrayRoundLength = roundLength.toCharArray();
String result = "";
for(int i = 0; i < arrayRoundLength.length; i ++) {
    if(shouldIncluded) {
        result += arrayRoundLength[i];
    }
}
```
6) было:
```
int sumSupport = 0;
int sumReal = data[0];

for(int i = 0; i < data.length; i ++) {
    sumSupport += data[i];
}

for(int i = 0; i < data.length; i ++) {
    if(data[i] * 2 == sumSupport) {
        sumReal = data[i];
        break;
    }
}
```
стало:
```
int sumSupport = 0;
for(int i = 0; i < data.length; i ++) {
    sumSupport += data[i];
}

int sumReal = data[0];
for(int i = 0; i < data.length; i ++) {
    if(data[i] * 2 == sumSupport) {
        sumReal = data[i];
        break;
    }
}
```
7) было:
```
String dif = "";
int debt = 0;
// много кода
for(int i = s1.length() - 1; i > -1; i --) {
    int curDig = (int) s1.charAt(i) - debt;
    boolean isLessNull = curDig < (int) s2.charAt(i);
    if(isLessNull) {
        dif = 10 + curDig - (int) s2.charAt(i) + dif;
        debt = 1;
    }
    if(! lessNull) {
        dif = curDig - (int) s2.charAt(i) + dif;
        debt = 0;
    }
}
```
стало:
```
// много кода
String dif = "";
int debt = 0;
for(int i = s1.length() - 1; i > -1; i --) {
    int curDig = (int) s1.charAt(i) - debt;
    boolean isLessNull = curDig < (int) s2.charAt(i);
    if(isLessNull) {
        dif = 10 + curDig - (int) s2.charAt(i) + dif;
        debt = 1;
    }
    if(! lessNull) {
        dif = curDig - (int) s2.charAt(i) + dif;
        debt = 0;
    }
}
```
8) было:
```
int numDig;
int lastDigit;
int res;
int numSyst = 8;
if(! octal) {
    numSyst = 16;
}

for(int i = 0; i < N; i ++) {
    res = 0;
    numDig = 0;
    while(data[i] > 0) {
        lastDigit = data[i] % 10;
        res += lastDigit * Math.pow(numSyst, numDig);
        numDig ++;
        data[i] = data[i] / 10;
    }
    data[i] = res;
}
```
стало:
```
int numSyst = 8;
if(! octal) {
    numSyst = 16;
}

int numDig;
int lastDigit;
int res;
for(int i = 0; i < N; i ++) {
    res = 0;
    numDig = 0;
    while(data[i] > 0) {
        lastDigit = data[i] % 10;
        res += lastDigit * Math.pow(numSyst, numDig);
        numDig ++;
        data[i] = data[i] / 10;
    }
    data[i] = res;
}
```
9) было:
```
int count = 1;
ArrayList<Integer> countOfSymb = new ArrayList<>();
char [] arrayOfChar = s.toCharArray();
Arrays.sort(arrayOfChar);
for(int i = 1; i < ar.length; i ++) {
    if(arrayOfChar[i] == arrayOfChar[i - 1]) {
        count ++;
        continue;
    }
    countOfSymb.add(count);
    count = 1;
}
```
стало:
```
char [] arrayOfChar = s.toCharArray();
Arrays.sort(arrayOfChar);
int count = 1;
ArrayList<Integer> countOfSymb = new ArrayList<>();
for(int i = 1; i < ar.length; i ++) {
    if(arrayOfChar[i] == arrayOfChar[i - 1]) {
        count ++;
        continue;
    }
    countOfSymb.add(count);
    count = 1;
}
```
10) было:
```
int [] arrayOfKeys = new int[k];
String resultOfOpenDoor = "";

for(int i = 1; i <= k; i ++) {
    for(int j = 0; j < k; j ++) {
        if(i == 1) {
            arrayOfKeys[j] = i;
            continue;
        }
        if((j + 1) % i == 0) {
            arrayOfKeys[j] = rev(arrayOfKeys[j]);
        }
    }
}

for(int j = 0; j < k; j ++) {
        resultOfOpenDoor += arrayOfKeys[j];
}
```
стало:
```
int [] arrayOfKeys = new int[k];
for(int i = 1; i <= k; i ++) {
    for(int j = 0; j < k; j ++) {
        if(i == 1) {
            arrayOfKeys[j] = i;
            continue;
        }
        if((j + 1) % i == 0) {
            arrayOfKeys[j] = rev(arrayOfKeys[j]);
        }
    }
}

String resultOfOpenDoor = "";
for(int j = 0; j < k; j ++) {
        resultOfOpenDoor += arrayOfKeys[j];
}
```
__Завершение работы с переменными:__

11) было:
```
int spaceCount = 0;
for(int j = 0; j < col; j ++) {
    int i;
    for(i = 0; i < row; i ++) {
        if(j * col + i + spaceCount < s.length()) {
            pack[i][j] = s.charAt(j * col + i + spaceCount);
        }
    }
    if(j * col + i + spaceCount < s.length() && s.charAt(j * col + i + spaceCount) == ' ') {
        spaceCount ++;
    }
}
```
стало:
```
int spaceCount = 0;
for(int j = 0; j < col; j ++) {
    int i;
    for(i = 0; i < row; i ++) {
        if(j * col + i + spaceCount < s.length()) {
            pack[i][j] = s.charAt(j * col + i + spaceCount);
        }
    }
    if(j * col + i + spaceCount < s.length() && s.charAt(j * col + i + spaceCount) == ' ') {
        spaceCount ++;
    }
}
spaceCount = -1;
```
12) присвоила переменной недопустимое значение после окончания работы с ней:
```
// много кода
Path = "ERROR";
```
13) аналогично присвоила переменной недопустимое значение после окончания работы с ней:
```
// много кода
yearOfTreeLife = -1;
```
__Добавление утверждений для проверки значений важных переменных:__

14) проверка суммарного расхода тонера:
```
assert sumСonsumption < 100000;
```
15) вывод предупреждения при обнаружении недопустимого значения:
```
if(velocity_kmh > VELOCITY_LIMIT_KMH) {
  log.info("Превышена максимально допустимая скорость.");
}
```
