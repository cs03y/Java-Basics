# 第 5 课：Java 数组与字符串

本课目标：

1. 理解数组的作用。
2. 学会创建和访问数组。
3. 掌握数组的遍历。
4. 学会求和、求最大值。
5. 了解字符串的常见操作。

## 一、数组是什么？

假设你需要保存 5 个学生的成绩。

如果不使用数组，你可能需要这样写：

```java
int score1 = 80;
int score2 = 90;
int score3 = 75;
int score4 = 88;
int score5 = 95;
```

如果有 100 个学生呢？

这时就需要数组。

数组可以理解为一个能够按位置存放多个同类型元素的容器。

例如：

```java
int[] scores = {80, 90, 75, 88, 95};
```

这个数组存储了 5 个整数。

结构如下：

| 下标 | 0 | 1 | 2 | 3 | 4 |
| --- | --- | --- | --- | --- | --- |
| 元素 | 80 | 90 | 75 | 88 | 95 |

注意：**数组下标从 0 开始，而不是从 1 开始。**

这是 Java 中最重要的基础知识之一。

## 二、如何访问数组元素？

假设有以下数组：

```java
int[] arr = {10, 20, 30, 40, 50};
```

访问第一个元素：

```java
System.out.println(arr[0]);
```

输出：

```text
10
```

访问第三个元素：

```java
System.out.println(arr[2]);
```

输出：

```text
30
```

为什么是 `arr[2]`？

因为下标从 0 开始：

```text
arr[0] = 10
arr[1] = 20
arr[2] = 30
arr[3] = 40
arr[4] = 50
```

如果访问：

```java
System.out.println(arr[5]);
```

就会发生数组下标越界异常，因为这个数组最大的有效下标是 `4`。

### 重要规律

如果数组长度为 `n`：

- 第一个元素的下标是 `0`。
- 最后一个元素的下标是 `n - 1`。
- 有效下标范围是 `0` 到 `n - 1`。

## 三、如何创建数组？

Java 中常见的数组创建方式有两种。

### 方式一：直接赋值

```java
int[] arr = {1, 2, 3, 4, 5};
```

适合已经知道所有元素的情况。

### 方式二：指定长度

```java
int[] arr = new int[5];
```

这表示创建一个长度为 5 的整数数组。

对于 `int` 数组，创建后所有元素默认都是 `0`。

例如：

```java
int[] arr = new int[5];

System.out.println(arr[0]);
System.out.println(arr[4]);
```

输出：

```text
0
0
```

你也可以修改元素：

```java
int[] arr = new int[3];

arr[0] = 10;
arr[1] = 20;
arr[2] = 30;

System.out.println(arr[1]);
```

输出：

```text
20
```

## 四、如何遍历数组？

遍历就是依次访问数组中的每一个元素。

例如：

```java
int[] arr = {10, 20, 30, 40, 50};

for (int i = 0; i < arr.length; i++) {
    System.out.println(arr[i]);
}
```

输出：

```text
10
20
30
40
50
```

这里有一个新知识：

```java
arr.length
```

它表示数组的长度。

对于这个数组：

```java
int[] arr = {10, 20, 30, 40, 50};
```

`arr.length` 的值是 `5`。

所以：

```java
for (int i = 0; i < arr.length; i++)
```

会依次访问下标 `0`、`1`、`2`、`3`、`4`。

记住：数组长度是 `5`，但最后一个下标是 `4`。

### 更简单的遍历方式

Java 还提供了增强 `for` 循环：

```java
int[] arr = {10, 20, 30};

for (int num : arr) {
    System.out.println(num);
}
```

输出：

```text
10
20
30
```

这里的 `num` 每次都会取得数组中的一个元素。

- 如果只需要读取元素，可以使用增强 `for`。
- 如果需要下标，或者要根据位置修改元素，通常使用普通 `for`。

## 五、数组的经典算法

现在我们开始接触真正的算法。

### 1. 计算数组的总和

例如：

```java
int[] arr = {10, 20, 30};

int sum = 0;

for (int i = 0; i < arr.length; i++) {
    sum += arr[i];
}

System.out.println(sum);
```

输出：

```text
60
```

理解执行过程：

| 当前元素 | sum 的计算 | sum 的值 |
| --- | --- | --- |
| 初始值 | `sum = 0` | `0` |
| `10` | `sum += 10` | `10` |
| `20` | `sum += 20` | `30` |
| `30` | `sum += 30` | `60` |

其中：

```java
sum += arr[i];
```

等价于：

```java
sum = sum + arr[i];
```

### 2. 查找数组中的最大值

例如：

```java
int[] arr = {7, 3, 15, 9, 2};

int max = arr[0];

for (int i = 1; i < arr.length; i++) {
    if (arr[i] > max) {
        max = arr[i];
    }
}

System.out.println(max);
```

输出：

```text
15
```

算法思路：

1. 先假设第一个元素最大。
2. 从第二个元素开始比较。
3. 如果发现更大的元素，就更新 `max`。
4. 遍历结束后，`max` 就是最大值。

注意：这里假设数组至少包含一个元素，因为我们使用了 `arr[0]`。

## 六、字符串 String

数组用于存储多个同类型的元素，而 `String` 用于表示文本。

例如：

```java
String name = "Java";
```

### 1. 获取字符串长度

```java
String s = "Hello";

System.out.println(s.length());
```

输出：

```text
5
```

注意区别：

| 对象 | 获取长度的方式 |
| --- | --- |
| 数组 | `arr.length` |
| 字符串 | `s.length()` |

数组使用 `length` 属性，字符串使用 `length()` 方法。

### 2. 获取指定位置的字符

```java
String s = "Java";

System.out.println(s.charAt(0));
System.out.println(s.charAt(2));
```

输出：

```text
J
v
```

和数组一样，字符串下标也从 `0` 开始。

### 3. 比较字符串

这是一个非常重要的知识点。

不要直接使用 `==` 判断两个字符串的内容是否相同。

推荐使用：

```java
String a = "Java";
String b = "Java";

System.out.println(a.equals(b));
```

输出：

```text
true
```

记住：

- 比较基本类型的数值是否相等，通常使用 `==`。
- 比较两个字符串的内容是否相同，通常使用 `equals()`。
