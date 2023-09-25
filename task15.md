**3.1.**

1.
```
boolean isBeginWithFoundIndex = map[i + j].indexOf(tanks[j], index) == index;
// проверяем, если текущая строка не начинается с ранее найденного индекса:
if(! isBeginWithFoundIndex)
```
2.
```
boolean isFailed = indexMove == 1 && indexNum == data.length - 1;
// проверяем, пройдена ли первичная проверка на возможность упорядочивания:
if(isFailed) {
  return false;
}
```
3.
```
boolean isRepeat = name.size() > j && pairs[0].equals(name.get(j));
// проверяем, встречалась ли ранее текущая позиция товара:
if(isRepeat)
```
4.
```
REQUIRED_NUMBER_OF_WALKERS = 3;
REQUIRED_SUM = 10;
boolean sumOfTwoElem = Character.getNumericValue(elem1) + Character.getNumericValue(elem2);
// проверяем, если количество ходоков не равно 3 между двумя элементами с суммой 10:
if(sumOfTwoElem == REQUIRED_SUM && countWalker != REQUIRED_NUMBER_OF_WALKERS) {
  // код
}
// в противном случае - ходок найден
if(sumOfTwoElem == REQUIRED_SUM && countWalker == REQUIRED_NUMBER_OF_WALKERS) {
  // код
}
```
5.
```
INVALID_CHAR = '0';
SEPARATOR_COMMA = ',';
boolean shouldIncluded = arrayRoundLength[i] != INVALID_CHAR && arrayRoundLength[i] != SEPARATOR_COMMA;
// проверяем, нужно ли включать символ в результирующую строку:
if(shouldIncluded)
```
6.
```
boolean isExist = (bytes[index] & curByte) == curByte && ! set.contains(arr[i]);
// проверяем, встречался ли элемент ранее:
if(isExist)
```
7.
```
boolean isTotalSum = data[i] * 2 == sumSupport;
// проверяем, является ли число суммой всех чисел:
if(isTotalSum)
```
**3.2**
1. было:
```
String ext1 = "jpg"; // искомое расширение
String ext2 = "png"; // новое расширение
```
стало:
```
String extensionForSearch = "jpg";
String newExtension = "png";
```
2. было:
```
int count0 = 0; // количество '0'
int count1 = 0; // количество '1'
int maxLen = 0; // длина максимальной найденной подстроки
```
стало:
```
int countOfNull = 0;
int countOfOnes = 0;
int maxLengthOfSubstring = 0;
```
3. было:
```
int curSum = 0; // текущая сумма элементов в массиве array
int count = 0; // количество элементов, составляющих текущую сумму
```
стало:
```
int sumOfArrayNums = 0;
int countOfArrayNums = 0;
```
Также в ранних кодах были замечены излишние комментарии для мест, очевидных для опытных программистов, например:
4. было:
```
String s = String.valueOf(x); // преобразуем число в строку
```
стало:
```
String convertIntToString = String.valueOf(x);
```
5. было:
```
int r = rand.nextInt(9) + 1; // случайное число от 1 до 9
```
стало:
```
int randomNumber = rand.nextInt(9) + 1;
```
