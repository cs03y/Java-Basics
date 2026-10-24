# 第 6 课：Java 方法与面向对象基础

本课目标：

1. 理解方法的作用。
2. 学会定义和调用方法。
3. 理解参数与返回值。
4. 认识类和对象。
5. 编写第一个面向对象程序。

## 第一部分：什么是方法？

假设你需要计算两个整数的和。

每次都写：

```java
int a = 10;
int b = 20;

System.out.println(a + b);
```

如果需要计算很多次，就会出现大量重复代码。

这时可以定义一个方法，让它负责计算。

### 1. 定义方法

```java
public static int add(int a, int b) {
    return a + b;
}
```

我们逐个理解。

| 代码 | 含义 |
| --- | --- |
| `public` | 访问修饰符 |
| `static` | 静态修饰符 |
| `int` | 返回值类型 |
| `add` | 方法名 |
| `int a, int b` | 两个参数 |
| `return a + b` | 返回计算结果 |

可以把这个方法理解成一台计算机器：

```text
输入 a = 10
输入 b = 20
     ↓
   add 方法
     ↓
  计算 10 + 20
     ↓
   返回 30
```

### 2. 调用方法

完整代码：

```java
public class Main {

    public static int add(int a, int b) {
        return a + b;
    }

    public static void main(String[] args) {
        int result = add(10, 20);

        System.out.println(result);
    }
}
```

输出：

```text
30
```

这里发生了什么？

1. 程序从 `main` 开始执行。
2. 调用 `add(10, 20)`。
3. 方法接收参数 `a = 10`、`b = 20`。
4. `return a + b` 返回 `30`。
5. 把返回值存入 `result`。
6. 输出 `result`。

核心：**方法让代码能够重复使用，避免重复编写相同的逻辑。**

## 第二部分：参数和返回值

这是 Java 方法最重要的两个概念。

### 1. 参数

参数是方法接收的输入。

例如：

```java
public static void greet(String name) {
    System.out.println("你好，" + name);
}
```

调用：

```java
greet("Tom");
greet("Alice");
```

输出：

```text
你好，Tom
你好，Alice
```

`name` 是参数，`"Tom"` 和 `"Alice"` 是调用时传入的实参。

### 2. 返回值

返回值是方法计算后交给调用者的结果。

例如：

```java
public static int square(int n) {
    return n * n;
}
```

调用：

```java
System.out.println(square(5));
```

输出：

```text
25
```

因为 `5 × 5 = 25`。

### 3. void 是什么？

有些方法只执行操作，不需要返回结果。

例如：

```java
public static void sayHello() {
    System.out.println("Hello!");
}
```

调用：

```java
sayHello();
```

输出：

```text
Hello!
```

区别：

- `int`：方法返回一个整数。
- `double`：方法返回一个小数。
- `String`：方法返回一个字符串。
- `void`：方法不返回结果。

注意：`void` 方法仍然可以执行 `return;` 提前结束，但不能通过 `return` 返回一个整数或字符串。

## 第三部分：什么是类和对象？

这是面向对象编程的基础。

你可以这样理解：

- **类（Class）**：描述某种事物的模板。
- **对象（Object）**：根据模板创建出来的具体实例。

例如，我们要描述学生。

学生通常有姓名、年龄，也可以执行自我介绍。

我们可以定义一个 `Student` 类。

```java
class Student {
    String name;
    int age;

    void introduce() {
        System.out.println("我是" + name + "，今年" + age + "岁");
    }
}
```

这里：

```java
String name;
int age;
```

表示学生对象拥有的属性。

而：

```java
void introduce()
```

表示学生可以执行的行为。

### 创建对象

```java
public class Main {
    public static void main(String[] args) {

        Student s = new Student();

        s.name = "Tom";
        s.age = 18;

        s.introduce();
    }
}
```

输出：

```text
我是Tom，今年18岁
```

理解以下代码：

```java
Student s = new Student();
```

可以拆成：

- `Student`：对象所属的类。
- `s`：引用变量的名称。
- `new Student()`：创建一个新的学生对象。

接下来：

```java
s.name = "Tom";
s.age = 18;
```

给对象的属性赋值。

最后：

```java
s.introduce();
```

调用对象的方法。

### 类和对象的关系

```text
          Student 类
       （学生的设计模板）
               ↓
          创建对象
               ↓
       ┌─────────────┐
       │ Student s1  │
       │ name = Tom  │
       │ age = 18    │
       └─────────────┘
```

同一个类可以创建多个对象，每个对象都可以有自己的属性值。

例如：

```java
Student s1 = new Student();
s1.name = "Tom";
s1.age = 18;

Student s2 = new Student();
s2.name = "Alice";
s2.age = 20;
```

这两个对象都属于 `Student` 类，但它们保存的信息不同。
