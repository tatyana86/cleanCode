__Уменьшение области видимости переменных:__

1) уменьшение области видимости spaceCount:
```
{
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
}
```
2) уменьшение области видимости difLen:
```
{
  int difLen = s1.length() - s2.length();
  if(difLen == 0) {
      for(int i = 0; i < s1.length(); i ++) {
          if((int) s1.charAt(i) < (int) s2.charAt(i)) {
              String sBuf = s1;
              s1 = s2;
              s2 = sBuf;
              break;
          }
      }
  }

  for(int i = 0; i < difLen; i ++) {
      s2 = "0" + s2;
  }
}
```
3) уменьшение области видимости countChar:
```
ArrayList<Integer> countOfSymb = new ArrayList<>();
char [] arrayOfChar = s.toCharArray();
Arrays.sort(arrayOfChar);
{
  int countChar = 1;
  for(int i = 1; i < arrayOfChar.length; i ++) {
      if(arrayOfChar[i] == arrayOfChar[i - 1]) {
          countChar ++;
          continue;
      }
      countOfSymb.add(countChar);
      countChar = 1;
  }
  countOfSymb.add(countChar);
}
```

__Выделение связанных команд в функции:__

4) выделила в отдельную функцию расчет длины линии при наборе пароля:
```
public static double countLengthOfLine(int [] arrayOfNumbers) {
  double length = 0.0;
  for(int i = 1; i < N; i ++) {
    int checkDif = Math.abs(hits[i - 1] - hits[i]);
    int checkSum = hits[i - 1] + hits[i];
    if(checkDif == 1 || checkSum == 7 || checkSum == 10) {
        length += 1;
    }
    else {
        length += Math. sqrt(2);
    }
  }
  return length;
}
```
5) выделила в отдельную функцию формирование строки без ведущих нулей:
```
public static String createStringWithoutNull(String difference) {
  String withoutNull = "";
  for(int i = 1; i < difference.length(); i ++) {
      char cur = difference.charAt(i);
      if(cur == '0' && withoutNull.length() == 0) {
          continue;
      }
      withoutNull += cur;
  }
  return withoutNull;
}
```
6) выделила в отдельную функцию формирование массива из цифр, записанных в строке:
```
public static int[] createArrayFromString(String input){
    int [] codeOfSymb = new int [input.length()];
    for(int i = 0; i < input.length(); i ++) {
        codeOfSymb[i] = (int) input.charAt(i);
    }
    return codeOfSymb;
}
```
В своих программах не обнаружила более мест, где можно было бы уменьшить время жизни переменных.
Попытки найти показательные примеры на github не дали значимых результатов (я искала через ключевое слово "pet project", не исключаю, что нужна иная тактика поиска "плохого" кода). Так, были найдены коды с объявлением переменных в начале функции/метода, в то время как переменная впервые используется намного позже.

При обнаржении примеров по данной теме в будущем - обновлю файл.
