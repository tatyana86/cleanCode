**Информативные комментарии**

1.
```
// генерируем случайное число и записываем его в файл:
bw.write(Integer.toString(rand.nextInt()));
```
2.
```
// добавляем в массив все содержимое с путями директории file
expand.addAll(Arrays.asList(file.listFiles()));
```
3.
```
// для поиска делителей числа достаточно проверить числа до половины числа + 1
for(int d = 2; d < (n / 2 + 1); d ++) { ... }
```
4.
```
// суммируем построчно целые числа из двух файлов
      for (int i = 1; i <= 3; i++) {
          String s1 = br1.readLine();
          String s2 = br2.readLine();
          sum = sum + Integer.valueOf(s1) + Integer.valueOf(s2);
      }
```
5.
```
private String getHtml(String url) throws IOException {
    // библиотека JSOUP является сторонней для работы с html страницами
    Document doc = Jsoup.connect(url).get();
    return doc.html();
}
```
6.
```
// проверяем правильность конфигурации
if (!Resource.checkConfig(config, CONFIG_IDENTIFICATOR, Double.parseDouble(CONFIG_VERSION)) { .. }
```

**Представление намерений**

7.
```
// проходимся по границам матрицы и записываем элементы
// верхняя строка:
for(int j = 0 + circle; j < m - circle; j ++) {
    spiralMatrix[index] = matrix[circle][j];
    index ++;
}

// правый столбец:
for(int i = 1 + circle; i < n - circle; i ++) {
    spiralMatrix[index] = matrix[i][m - 1 - circle];
    index ++;
}

// нижняя строка:
for(int j = m - 2 - circle; j >= circle; j --) {
    spiralMatrix[index] = matrix[n - 1 - circle][j];
    index ++;
}

// левый столбец
for(int i = n - 2 - circle; i > circle; i --) {
    spiralMatrix[index] = matrix[i][circle];
    index ++;
}
```

**Усиление**

8.
```
// обязательно очищаем массив, т.к. в нем записаны неактуальные пути
expand.clear();
```
9.
```
// умножаем на 1.0, чтобы получить дробное число,
// так как среднее число может не быть целым
averageValue = 1.0 * sumOfNumbers / (M - N + 1);

```
10.
```
// проверяем, успешно ли удаление исходной директории
// т.к. если во время выполнения программы какой-либо файл открыт,
// то удалить директорию не удастся
if(root.exists())
    return false;
```

**TODO-комментарии**

11.
```
public Integer call() {
  // TODO - заглушка, чтобы скомпилировать. Необходимо доработать в следующей версии
  return 0;
}
```
12.
```
// TODO - дополнить метод, чтобы при переполнении выбрасывалось исключение
```
