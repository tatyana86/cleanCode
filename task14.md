**Замена на более безопасные структуры данных:**

1. было:
```
public static int odometer(int [] oksana)
  {
    int distance = 0;
    int lastTime = 0;

    for(int i = 1; i < oksana.length; i += 2) {
        distance += (oksana[i] - lastTime) * oksana[i - 1];
        lastTime = oksana[i];
    }

    return distance;
  }
```
Можно заменить массив ```int [] oksana``` на связный список:
```
public static int odometer(LinkedList oksana) {
    int distance = 0;
    int lastTime = 0;

    Node node = oksana.head;
    while (node != null) {
        distance += (node.next.value - lastTime) * node.value;
        lastTime = node.next.value;
        node = node.next.next;
    }

    return distance;
}
```
2. было:
```
public static int SumOfThe(int N, int [] data) {
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

    return sumReal;
}
```
Аналогично можно заменить массив ```int [] data``` на связный список:
```
public static int SumOfThe(int N, LinkedList data) {
    int sumSupport = 0;
    int sumReal = data.head.value;

    Node nodeForSum = data.head;
    while (nodeForSum != null) {
        sumSupport += nodeForSum.value;
        nodeForSum = nodeForSum.next;
    }

    Node node = data.head;
    while (node != null) {
        if(node.value * 2 == sumSupport) {
            sumReal = node.value;
            break;
        }
        node = node.next;
    }

    return sumReal;
}
```
**Работа с массивом без прямой индексации:**

3. было:
```
for(int i = 0; i < data.length; i ++) {
    sumSupport += data[i];
}
```
стало:
```
for(int number : data) {
    sumSupport += number;
}
```
4. было:
```
for(int j = 0; j < k; j ++) {
        res += keys[j];
}
```
стало:
```
for(int key : keys) {
        res += key;
}
```
5. было:
```
for(int i = 0; i < arrayRoundLength.length; i ++) {
    boolean shouldIncluded = arrayRoundLength[i] != '0' && arrayRoundLength[i] != ',';
    if(shouldIncluded) {
        result += arrayRoundLength[i];
    }
}
```
стало:
```
for(char charOfDigit : arrayRoundLength) {
    boolean shouldIncluded = charOfDigit != '0' && charOfDigit != ',';
    if(shouldIncluded) {
        result += charOfDigit;
    }
}
```
