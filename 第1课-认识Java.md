# 第 1 课：认识 Java

## 1. Java 是什么？

Java 是一种广泛使用的编程语言，常用于：

- 后端开发
- Android 应用开发
- 企业级软件
- 大型业务系统
- 算法与数据结构学习

Java 的一个重要特点是：编译后的字节码可以在不同平台的 Java 虚拟机上运行。

基本过程：

```text
Java 源代码
    ↓
Java 编译器 javac
    ↓
字节码文件 .class
    ↓
Java 虚拟机 JVM
    ↓
程序运行
```

三个重要概念：

| 名称 | 作用 |
| --- | --- |
| JDK | Java 开发工具包，包含编译和开发所需的工具 |
| JVM | Java 虚拟机，负责执行字节码 |
| javac | Java 编译器，将源代码编译成字节码 |

初学时，你只需要记住：**编写代码、编译代码、运行程序。**

## 2. 第一个 Java 程序

看看下面的代码：

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Hello Java!");
    }
}
```

运行后输出：

```text
Hello Java!
```

我们逐行理解。

### 第一行

```java
public class Main {
```

- `public`：访问修饰符。
- `class`：声明一个类。
- `Main`：类名。
- `{`：表示代码块开始。

你可以先把类理解成组织 Java 代码的一种基本结构。

### 第二行

```java
public static void main(String[] args) {
```

这是 Java 程序常见的入口方法。

暂时不必背诵所有细节，先记住：

- `public`：访问权限。
- `static`：静态修饰符。
- `void`：表示方法不返回结果。
- `main`：程序入口方法的名称。
- `String[] args`：用于接收命令行传入的字符串参数。

现阶段，你只需要知道程序从 `main` 方法开始执行。

### 第三行

```java
System.out.println("Hello Java!");
```

这行代码负责输出内容。

- `System.out`：标准输出对象。
- `println()`：输出内容后换行。
- `"Hello Java!"`：要输出的字符串。
- `;`：语句结束标记。

例如：

```java
System.out.println("你好");
System.out.println("Java");
```

输出：

```text
你好
Java
```

如果使用 `print()`：

```java
System.out.print("你好");
System.out.print("Java");
```

输出：

```text
你好Java
```

区别：`println()` 输出后换行，`print()` 输出后不主动换行。

## 3. Java 的基本规则

先掌握这三个规则：

1. Java 是区分大小写的，`Main` 和 `main` 不一样。
2. 大多数语句以分号 `;` 结尾。
3. 一对 `{}` 用于划分代码块。

例如：

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("第一行");
        System.out.println("第二行");
    }
}
```

注意：如果类声明为 `public class Main`，通常应将源代码保存为 `Main.java`。
