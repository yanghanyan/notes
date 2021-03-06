<!-- GFM-TOC -->
- [一、Java概述](#一Java概述)
  * [1、Java语言发展史](#1Java语言发展史)
  * [2、JVM JRE JDK的概述](#2JVM-JRE-JDK的概述)
    + [2.1、什么是跨平台?](#21什么是跨平台&quest;)
    + [2.2、JVM JRE JDK](#22JVM-JRE-JDK)
- [二、数据类型](#二数据类型)
  * [1、基本数据类型](#1基本数据类型)
  * [2、包装类型](#2包装类型)
  * [3、数据类型转换](#3数据类型转换)
    + [3.1、隐式转换](#31隐式转换)
    + [3.2、强制转换](#32强制转换)
  * [4、缓存池](#4缓存池)
- [三、String](#三string)
  * [1、概览](#1概览)
  * [2、不可变的好处](#2不可变的好处)
    + [2.1、可以缓存 hash 值](#21可以缓存-hash-值)
    + [2.2、String Pool 的需要](#22String-Pool-的需要)
    + [2.3、安全性](#23安全性)
    + [2.4、线程安全](#24线程安全)
  * [3、String, StringBuffer and StringBuilder](#3String--StringBuffer-and-StringBuilder)
    + [3.1、可变性](#31可变性)
    + [3.2、线程安全](#32线程安全)
  * [4、String Pool](#4String-Pool)
  * [5、new String("abc")](#5new-String-"abc"-)
- [四、运算符](#四运算符)
  * [1、算数运算符](#1算数运算符)
  * [2、移位运算符](#2移位运算符)
    + [2.1、左移运算符（<<）](#21左移运算符-<<-)
    + [2.2、有符号右移运算符（>>）](#22有符号右移运算符->>-)
    + [2.3、无符号右移运算符（>>>）](#23无符号右移运算符->>>-)
  * [3、赋值运算符](#3赋值运算符)
  * [4、关系运算符](#4关系运算符)
  * [5、逻辑运算符](#5逻辑运算符)
  * [6、三元运算符](#6三元运算符)
  * [7、位运算符](#7位运算符)
    + [7.1、&（与位运算）](#71&-与位运算-)
    + [7.2、|（或位运算）](#72|-或位运算-)
    + [7.3、~（非位运算）](#73~-非位运算-)
    + [7.4、^（异或位运算）](#74^-异或位运算-)
- [五、流程控制语句](#五流程控制语句)
  * [1、选择流程控制语句](#1选择流程控制语句)
    + [1.1、if](#11if)
    + [1.2、switch](#12switch)
  * [2、循环流程控制语句](#2循环流程控制语句)
    + [2.1、for](#21for)
    + [2.2、while](#22while)
    + [2.3、do ... while](#23do-----while)
    + [2.4、三种循环区别](#24三种循环区别)
  * [3、控制循环语句](#3控制循环语句)
- [六、方法（函数）](#方法-函数-)
  * [1、方法中参数传递](#1方法中参数传递)
  * [2、重写(Override)](#2重写-Override-)
  * [3、重载(Overload)](#3重载-Overload-)
- [七、关键字](#七关键字)
  * [1、final](#1final)
    + [1.1、修饰变量](#11修饰变量)
    + [1.2、修饰方法](#12修饰方法)
    + [1.3、修饰类](#13修饰类)
  * [2、static](#2static)
    + [2.1、修饰变量](#21修饰变量)
    + [2.2、修饰方法](#22修饰方法)
    + [2.3、修饰代码块](#23修饰代码块)
    + [2.4、修饰内部类](#24修饰内部类)
    + [2.5、静态导包](#25静态导包)
- [八、继承、抽象、多态](#八继承、抽象、多态)
  * [1、继承](#1继承)
    + [1.1、概述](#11概述)
    + [1.2、格式](#12格式)
    + [1.3、继承的特点](#13继承的特点)
    + [1.4、继承中成员的特点](#14继承中成员的特点)
    + [1.5、继承的利弊](#15继承的利弊)
    + [1.6、this和super](#16-this和super)
    + [1.7、初始化顺序](#17初始化顺序)
  * [2、抽象](#2抽象)
    + [2.1、抽象类](#21抽象类)
      - [2.1.1、概述](#211概述)
      - [2.1.2、格式](#212格式)
      - [2.1.3、特点](#213特点)
      - [2.1.4、abstract关键字不能和哪些关键字共存](#214abstract关键字不能和哪些关键字共存)
    + [2.2、接口](#22接口)
      - [2.2.1、概述](#221概述)
      - [2.2.2、格式](#222格式)
      - [2.2.3、特点](#223特点)
      - [2.2.4、优点](#224优点)
      - [2.2.5、接口和类的关系](#225接口和类的关系)
    + [2.3、接口与抽象类的区别](#23接口与抽象类的区别)
      - [2.3.1、共性](#231共性)
      - [2.3.2、区别](#232区别)
  * [3、多态](#3多态)
    + [3.1、概述](#31概述)
    + [3.2、格式](#32格式)
    + [3.3、多态前提](#33多态前提)
    + [3.4、多态下成员调用的特点](#34多态下成员调用的特点)
    + [3.5、多态下的类型转换](#35多态下的类型转换)
    + [3.6、多态优缺点](#36多态优缺点)
- [九、反射](#九反射)
  * [1、概述](#1概述)
  * [2、字节码对象](#2字节码对象)
  * [3、Class类](#3Class类)
    + [3.1、反射操作构造方法](#31反射操作构造方法)
    + [3.2、反射操作成员变量](#32反射操作成员变量)
    + [3.3、反射获取成员方法](#33反射获取成员方法)
  * [4、反射的优点](#4反射的优点)
  * [5、反射的缺点](#5反射的缺点)
- [十、泛型](#十泛型)
  * [1、概述](#1概述)
  * [2、优点](#2优点)
  * [3、限定通配符](#3限定通配符)
  * [4、非限定通配符](#4非限定通配符)
- [十一、异常](#十一异常)
  * [1、概述](#1概述)
  * [2、异常体系](#2异常体系)
  * [3、处理异常](#3处理异常)
    + [3.1、默认抛出(throws)](#31默认抛出(throws))
    + [3.2、捕获异常(try...catch...)](#32捕获异常(try...catch...))
  * [4、throw和throws的区别](#4throw和throws的区别)
  * [5、自定义异常](#5自定义异常)
- [十二、Object 通用方法](#十二Object-通用方法)
  * [1、概览](#1概览)
  * [2、hashCode()](#2hashCode--)
  * [3、equals()](#3equals--)
  * [4、clone()](#4clone--)
    + [4.1、浅拷贝](#41浅拷贝)
    + [4.2、深拷贝](#42深拷贝)
    + [4.3、clone()的替代方案](#43clone--的替代方案)
  * [5、toString()](#5tostring--)
  * [6、notify()](#6notify--)
  * [7、wait()](#7wait--)
  * [8、finalize()](#8finalize--)
- [十三、注解](#十三注解)
- [参考资料](#参考资料)
<!-- GFM-TOC -->


一、Java概述
=================

## 1、Java语言发展史
　　詹姆斯·高斯林（James Gosling）1977年获得了加拿大卡尔加里大学计算机科学学士学位，1983年获得了美国卡内基梅隆大学计算机科学博士学位，毕业后到IBM工作，设计IBM第一代工作站NeWS系统，但不受重视。后来转至Sun公司，1990年，与Patrick，Naughton和Mike Sheridan等人合作“绿色计划”，后来发展一套语言叫做“Oak”，后改名为Java。

　　SUN(Stanford University Network，斯坦福大学网络公司) 

## 2、JVM JRE JDK的概述
### 2.1、什么是跨平台?
- **平台**：指的是操作系统(Windows,Linux,Mac)
- **跨平台**：Java程序可以在任意操作系统上运行，一次编写到处运行
- **原理**：实现跨平台需要依赖Java的虚拟机 JVM (Java Virtual Machine)

### 2.2、JVM JRE JDK
- **JVM**：JVM是java虚拟机(JVM Java Virtual Machine)，java程序需要运行在虚拟机上，不同平台有自己的虚拟机，因此java语言可以跨平台
- **JRE**：包括Java虚拟机(JVM Java Virtual Machine)和Java程序所需的核心类库等如果想要运行一个开发好的Java程序，计算机中只需要安装JRE即可。
- **JDK**：JDK是提供给Java开发人员使用的，其中包含了java的开发工具，也包括了JRE。所以安装了JDK，就不用在单独安装JRE了。其中的开发工具：编译工具(javac.exe)  打包工具(jar.exe)等


二、数据类型
=================

## 1、基本数据类型

| 数据种类 | 数据类型 |     位      | 默认   | 范围             |
| :----:  |  :----: |     :----:   | :----: |     :----:       |
|   整形  |  byte   | 8bit，有符号  | 0      | -128 ~ 127       |
|         | short   | 16bit，有符号 | 0      | -32768 ~ 32767   |
|         | int     | 32bit，有符号 | 0      |-2^31 ~ 2^31 - 1  |
|         | long    | 64bit，有符号 | 0 L    | -2^63 ~ 2^63-1   |
|  浮点型 | float   | 32bit，单精度 | 0.0 f  | |
|         | double  | 64bit，双精度 | 0.0 d | |
|  字符型 | char    | 16bit，Unicode字符 |   | \u0000 ~ \uffff (0 ~ 65535)|
|  布尔型 | boolean | 1bit         | false  | true/false       |

　　boolean 只有两个值：true、false，可以使用 1 bit 来存储，但是具体大小没有明确规定。JVM 会在编译时期将 boolean 类型的数据转换为 int，使用 1 来表示 true，0 表示 false。JVM 支持 boolean 数组，但是是通过读写 byte 数组来实现的。

## 2、包装类型
　　基本类型都有对应的包装类型，基本类型与其对应的包装类型之间的赋值使用自动装箱与拆箱完成。

```java
Integer x = 2;     // 装箱 调用了 Integer.valueOf(2)
int y = x;         // 拆箱 调用了 X.intValue()
```

## 3、数据类型转换
### 3.1、隐式转换
　　取值范围小的数据类型与取值范围大的数据类型进行运算，会先将小的数据类型提升为大的，再运算。

### 3.2、强制转换
- **格式**：
```java
b = (byte)(a + b); 
```
- **注意**：如果超出了被赋值的数据类型的取值范围得到的结果会与你期望的结果不同

使用 += 或者 ++ 运算符会执行隐式类型转换。

```java
s1 += 1;
s1++;
```

## 4、缓存池

new Integer(123) 与 Integer.valueOf(123) 的区别在于：

- new Integer(123) 每次都会新建一个对象；
- Integer.valueOf(123) 会使用缓存池中的对象，多次调用会取得同一个对象的引用。

```java
Integer x = new Integer(123);
Integer y = new Integer(123);
System.out.println(x == y);    // false
Integer z = Integer.valueOf(123);
Integer k = Integer.valueOf(123);
System.out.println(z == k);   // true
```

valueOf() 方法的实现比较简单，就是先判断值是否在缓存池中，如果在的话就直接返回缓存池的内容。

```java
public static Integer valueOf(int i) {
    if (i >= IntegerCache.low && i <= IntegerCache.high)
        return IntegerCache.cache[i + (-IntegerCache.low)];
    return new Integer(i);
}
```

在 Java 8 中，Integer 缓存池的大小默认为 -128\~127。

```java
static final int low = -128;
static final int high;
static final Integer cache[];

static {
    // high value may be configured by property
    int h = 127;
    String integerCacheHighPropValue =
        sun.misc.VM.getSavedProperty("java.lang.Integer.IntegerCache.high");
    if (integerCacheHighPropValue != null) {
        try {
            int i = parseInt(integerCacheHighPropValue);
            i = Math.max(i, 127);
            // Maximum array size is Integer.MAX_VALUE
            h = Math.min(i, Integer.MAX_VALUE - (-low) -1);
        } catch( NumberFormatException nfe) {
            // If the property cannot be parsed into an int, ignore it.
        }
    }
    high = h;

    cache = new Integer[(high - low) + 1];
    int j = low;
    for(int k = 0; k < cache.length; k++)
        cache[k] = new Integer(j++);

    // range [-128, 127] must be interned (JLS7 5.1.7)
    assert IntegerCache.high >= 127;
}
```

　　编译器会在自动装箱过程调用 valueOf() 方法，因此多个值相同且值在缓存池范围内的 Integer 实例使用自动装箱来创建，那么就会引用相同的对象。

```java
Integer m = 123;
Integer n = 123;
System.out.println(m == n); // true
```

基本类型对应的缓冲池如下：

- boolean values true and false
- all byte values
- short values between -128 and 127
- int values between -128 and 127
- char in the range \u0000 to \u007F

在使用这些基本类型对应的包装类型时，如果该数值范围在缓冲池范围内，就可以直接使用缓冲池中的对象。

在 jdk 1.8 所有的数值类缓冲池中，Integer 的缓冲池 IntegerCache 很特殊，这个缓冲池的下界是 - 128，上界默认是 127，但是这个上界是可调的，在启动 jvm 的时候，通过 -XX:AutoBoxCacheMax=&lt;size&gt; 来指定这个缓冲池的大小，该选项在 JVM 初始化的时候会设定一个名为 java.lang.IntegerCache.high 系统属性，然后 IntegerCache 初始化的时候就会读取该系统属性来决定上界。

[StackOverflow : Differences between new Integer(123), Integer.valueOf(123) and just 123
](https://stackoverflow.com/questions/9030817/differences-between-new-integer123-integer-valueof123-and-just-123)


三、String
=================

## 1、概览
- String 被声明为 final，因此它不可被继承。(Integer 等包装类也不能被继承）
- 在 Java 8 中，String 内部使用 char 数组存储数据。
  ```java
  public final class String
      implements java.io.Serializable, Comparable<String>, CharSequence {
      /** The value is used for character storage. */
      private final char value[];
  }
  ```
- 在 Java 9 之后，String 类的实现改用 byte 数组存储字符串，同时使用 `coder` 来标识使用了哪种编码。
  ```java
  public final class String
      implements java.io.Serializable, Comparable<String>, CharSequence {
      /** The value is used for character storage. */
      private final byte[] value;

      /** The identifier of the encoding used to encode the bytes in {@code value}. */
      private final byte coder;
  }
  ```
- value 数组被声明为 final，这意味着 value 数组初始化之后就不能再引用其它数组。并且 String 内部没有改变 value 数组的方法，因此可以保证 String 不可变。
- **String(String original)**:把字符串数据封装成字符串对象
- **String(char[] value)**:把字符数组的数据封装成字符串对象
- **String(char[] value, int index, int count)**:把字符数组中的一部分数据封装成字符串对象

　　**注意：通过构造方法创建字符串对象是在堆内存，直接赋值方式创建对象是在方法区的常量池**。

## 2、不可变的好处
### 2.1、可以缓存 hash 值
　　因为 String 的 hash 值经常被使用，例如 String 用做 HashMap 的 key。不可变的特性可以使得 hash 值也不可变，因此只需要进行一次计算。

### 2.2、String Pool 的需要
　　如果一个 String 对象已经被创建过了，那么就会从 String Pool 中取得引用。只有 String 是不可变的，才可能使用 String Pool。

<div align="center"> <img src="https://cs-notes-1256109796.cos.ap-guangzhou.myqcloud.com/image-20191210004132894.png"/> </div><br>

### 2.3、安全性
　　String 经常作为参数，String 不可变性可以保证参数不可变。例如在作为网络连接参数的情况下如果 String 是可变的，那么在网络连接过程中，String 被改变，改变 String 的那一方以为现在连接的是其它主机，而实际情况却不一定是。

### 2.4、线程安全  
　　String 不可变性天生具备线程安全，可以在多个线程中安全地使用。

[Program Creek : Why String is immutable in Java?](https://www.programcreek.com/2013/04/why-string-is-immutable-in-java/)

## 3、String, StringBuffer and StringBuilder
### 3.1、可变性
- String 不可变
- StringBuffer 和 StringBuilder 可变

### 3.2、线程安全
- String 不可变，因此是线程安全的
- StringBuilder 不是线程安全的
- StringBuffer 是线程安全的，内部使用 synchronized 进行同步

[StackOverflow : String, StringBuffer, and StringBuilder](https://stackoverflow.com/questions/2971315/string-stringbuffer-and-stringbuilder)

## 4、String Pool
　　字符串常量池（String Pool）保存着所有字符串字面量（literal strings），这些字面量在编译时期就确定。不仅如此，还可以使用 String 的 intern() 方法在运行过程将字符串添加到 String Pool 中。

　　当一个字符串调用 intern() 方法时，如果 String Pool 中已经存在一个字符串和该字符串值相等（使用 equals() 方法进行确定），那么就会返回 String Pool 中字符串的引用；否则，就会在 String Pool 中添加一个新的字符串，并返回这个新字符串的引用。

　　下面示例中，s1 和 s2 采用 new String() 的方式新建了两个不同字符串，而 s3 和 s4 是通过 s1.intern() 方法取得同一个字符串引用。intern() 首先把 s1 引用的字符串放到 String Pool 中，然后返回这个字符串引用。因此 s3 和 s4 引用的是同一个字符串。

```java
String s1 = new String("aaa");
String s2 = new String("aaa");
System.out.println(s1 == s2);           // false
String s3 = s1.intern();
String s4 = s1.intern();
System.out.println(s3 == s4);           // true
```

　　如果是采用 "bbb" 这种字面量的形式创建字符串，会自动地将字符串放入 String Pool 中。

```java
String s5 = "bbb";
String s6 = "bbb";
System.out.println(s5 == s6);  // true
```

　　在 Java 7 之前，String Pool 被放在运行时常量池中，它属于永久代。而在 Java 7，String Pool 被移到堆中。这是因为永久代的空间有限，在大量使用字符串的场景下会导致 OutOfMemoryError 错误。

- [StackOverflow : What is String interning?](https://stackoverflow.com/questions/10578984/what-is-string-interning)
- [深入解析 String#intern](https://tech.meituan.com/in_depth_understanding_string_intern.html)

## 5、new String("abc")
　　使用这种方式一共会创建两个字符串对象（前提是 String Pool 中还没有 "abc" 字符串对象）。

- "abc" 属于字符串字面量，因此编译时期会在 String Pool 中创建一个字符串对象，指向这个 "abc" 字符串字面量；
- 而使用 new 的方式会在堆中创建一个字符串对象。

　　创建一个测试类，其 main 方法中使用这种方式来创建字符串对象。

```java
public class NewStringTest {
    public static void main(String[] args) {
        String s = new String("abc");
    }
}
```

　　使用 javap -verbose 进行反编译，得到以下内容：

```java
// ...
Constant pool:
// ...
   #2 = Class              #18            // java/lang/String
   #3 = String             #19            // abc
// ...
  #18 = Utf8               java/lang/String
  #19 = Utf8               abc
// ...

  public static void main(java.lang.String[]);
    descriptor: ([Ljava/lang/String;)V
    flags: ACC_PUBLIC, ACC_STATIC
    Code:
      stack=3, locals=2, args_size=1
         0: new           #2                  // class java/lang/String
         3: dup
         4: ldc           #3                  // String abc
         6: invokespecial #4                  // Method java/lang/String."<init>":(Ljava/lang/String;)V
         9: astore_1
// ...
```

　　在 Constant Pool 中，#19 存储这字符串字面量 "abc"，#3 是 String Pool 的字符串对象，它指向 #19 这个字符串字面量。在 main 方法中，0: 行使用 new #2 在堆中创建一个字符串对象，并且使用 ldc #3 将 String Pool 中的字符串对象作为 String 构造函数的参数。

　　以下是 String 构造函数的源码，可以看到，在将一个字符串对象作为另一个字符串对象的构造函数参数时，并不会完全复制 value 数组内容，而是都会指向同一个 value 数组。
```java
public String(String original) {
    this.value = original.value;
    this.hash = original.hash;
}
```


四、运算符
=================

## 1、算数运算符
　　既是数学中的加、减、乘、除等运算。因算术运算符是运算两个操作符，故又称为二元运算符。

- **概览**：对常量和变量进行操作的符号。如下：
 	```java
	+  -  *  /  %  ++  --
	```
- **%**：取余运算符。得到的是两个相除数据的余数。
- **++**：自增1，++在前，先增后用；++在后，先用后增。
- **--**：自减1，--在前，先减后用；--在后，先用后减。

　　这些操作可以对不同类型的数字进行混合运算，为了保证操作的精度，系统在运算过程中会做相应的转化。

## 2、移位运算符

### 2.1、左移运算符（<<）
　　将运算符左边的对象向左移动运算符右边指定的位数（在低位补0）

### 2.2、有符号右移运算符（>>）
　　将运算符左边的对象向右移动运算符右边指定的位数。如果值为正，则在高位补0，如果值为负，则在高位补1.

### 2.3、无符号右移运算符（>>>）
　　将运算符左边的对象向右移动运算符右边指定的位数。无论值的正负，都在高位补0.

## 3、赋值运算符
```java
	=  +=  -=  *=  /=  %=
```

## 4、关系运算符
　　关系运算符产生的结果都是布尔型的值，一般情况下，在逻辑与控制中会经常使用关系运算符，用于选择控制的分支，实现逻辑要求。
```java
>  <  >=  <=  ==  !=
instanceof(Java特有)
```
　　注意：

　　关系运算符中的"=="和"!="既可以操作基本数据类型，也可以操作引用数据类型。操作引用数据类型时，比较的是引用的内存地址。所以在比较非基本数据类型时，应该使用equals方法。

## 5、逻辑运算符
	逻辑运算符一般用于连接boolean类型的表达式或者值
	&（逻辑与运算符）：有false则false  
	|（逻辑或运算符）：有true则true
	&&（逻辑与运算符）：具有短路效果，左边为false，则右边不执行
	||（逻辑或运算符）：具有短路效果，左边为true，则右边不执行
	^（逻辑异或运算符）：相同为false，不同为true
	!（逻辑非运算符）：取反，非false则true，非true则false。

## 6、三元运算符
```java
- 格式：(关系表达式)?表达式1：表达式2；
	如果条件为true，运算后的结果是表达式1；
	如果条件为false，运算后的结果是表达式2；
```

## 7、位运算符

### 7.1、&（与位运算）
	两个数位都为1，结果才为1，否则结果为0

### 7.2、|（或位运算）
	两个数位只要有一个为1，那么结果就是1，否则就为0

### 7.3、~（非位运算）
	如果数位为0，结果是1，如果位为1，结果是0

### 7.4、^（异或位运算）
	两个数位相同则结果为0，不同则结果为1。任何数与0进行异或，为它本身

- 运算法则：
```
	　a ^ b = b ^ a
　　a ^ b ^ c = a ^ (b ^ c) = (a ^ b) ^ c;
　　d = a ^ b ^ c  --->  a = d ^ b ^ c.
　　a ^ b ^ a = b.
```


五、流程控制语句
=================

## 1、选择流程控制语句
### 1.1、if
**if语句格式**：

```java
// 第一种
if(关系表达式) {

}

// 第二种
if(关系表达式) {
		 语句体1;
} else {
		 语句体2;
}

// 第三种
if(关系表达式1) {
		   语句体1;
} else  if (关系表达式2) {
		  语句体2;
} ......
  else {
		  语句体n;
}
```

### 1.2、switch
- switch语句格式：
```java
switch (表达式) {
    case 值1:
        语句体1;
        break;
    case 值2:
        语句体2;
        break;
        ...
    default:
        语句体n + 1;
        break;
}
```

- 表达式支持的数据类型：
char, byte, short, int, Character, Byte, Short, Integer, String, enum

switch 不支持 long，是因为 switch 的设计初衷是对那些只有少数几个值的类型进行等值判断，如果值过于复杂，那么还是用 if 比较合适。

[StackOverflow : Why can&#39;t your switch statement data type be long, Java?](https://stackoverflow.com/questions/2676210/why-cant-your-switch-statement-data-type-be-long-java)

## 2、循环流程控制语句
### 2.1、for
- for语句格式：
```java
for (初始化语句; 判断条件语句; 控制条件语句) {
    循环体语句;
}
```

### 2.2、while
- while语句格式
```java
while (判断条件语句) {
    循环体语句;
    控制条件语句;
}
```

### 2.3、do ... while
- do ... while语句格式
```java
初始化语句;
do {
    循环体语句;
    控制条件语句;
} while (判断条件语句);
```

### 2.4、三种循环区别
- do…while循环至少会执行一次循环体
- 控制条件语句所控制的那个变量，在for循环结束后，就不能再被访问到了，而while循环结束还可以继续使用

## 3、控制循环语句
- continue：结束一次循环，继续下一次的循环
- break：跳出循环，让循环提前结束


六、方法（函数）
=================

**完成特定功能的代码块，提高代码的复用性，降低冗余度**。

- 格式：
```java
修饰符 返回值类型 方法名(参数列表) {
    方法体;
    return;
}
```

## 1、方法中参数传递
- **基本数据类型**(传递的是值，不影响原来方法的变量的值)
  ```java
  public static void main(String[] args) {
      int a = 10;
      add(a);
      int b = 20;
      add(b);

      System.out.println(a);  // 10
      System.out.println(b);  // 20
  }

  public static void add(int value) {
      ++value;
  }
  ```

- **引用数据类型**(传递的是地址值，可以修改内存中的值)
  ```java
  public static void main(String[] args) {
      int[] arr = {1,2,3};
      change(arr);

      System.out.println(Arrays.toString(arr));  // [0, 2, 3]
  }

  public static void change(int[] arr) {
      arr[0] = 0;
  }
  ```

## 2、重写(Override)
　　在子父类中，子类对父类中的方法进行重新定义的过程，因为父类的方法可能不能完全满足子类的需求

　　**方法重写的注意事项：两同两小一大**。
- **两同**：方法名、参数列表一定要相同
- **两小**：子类方法的返回类型、抛出异常类型 <= 父类方法的返回类型、抛出异常类型
- **一大**：子类方法的权限修饰符 >= 父类方法的权限修饰符

　　使用 @Override 注解，可以让编译器帮忙检查是否满足上面的三个限制条件。

## 3、重载(Overload)
- **特点**：存在于同一个类中，指一个方法与已经存在的方法名称上相同，但是参数类型、个数、顺序至少有一个不同。应该注意的是，返回值不同，其它都相同不算是重载。
- **应用场景**：时间比较工具类，每个方法传入参数格式不同
  ```java
    public boolean compareDateTime(Date date, Date date2) {
        ...
    }

    public boolean compareDateTime(String date, String date2) {
        ...
    }

    public boolean compareDateTime(String date) {
        ...
    }
  ```


七、关键字
=================

## 1、final

### 1.1、修饰变量
　　**修饰成员变量或局部变量则为不能被改变的常量**。
- 对于基本类型，final 使数值不变；
- 对于引用类型，final 使引用地址值不变，但是被引用的对象本身是可以修改的。

### 1.2、修饰方法
　　**被final修饰的方法不能够被继承、重写**。final修饰方法的一个好处是可以提高运行效率，编译器遇到final方法会转入内嵌机制。

　　private 方法隐式地被指定为 final，如果在子类中定义的方法和基类中的一个 private 方法签名相同，此时子类的方法不是重写基类方法，而是在子类中定义了一个新的方法。

### 1.3、修饰类
　　**被final修饰的类不能够被继承**。

## 2、static
　　**它是静态修饰符，是一个关键字，可以修饰类的成员变量、成员方法及代码块**。
- **优点**：随着类的加载而加载，被static修饰的成员被类的实例所共享，我们可以通过static关键字实现不创建对象，就可以类名.的方式直接调用其所属的成员。
- **弊端（局限性）**：**静态只能调用静态成员，不能调用非静态的成员**。

### 2.1、修饰变量
- **被static修饰的变量为静态变量，静态变量在内存中只存在一份**。

### 2.2、修饰方法
- **被static修饰的方法为静态方法，静态方法不可以被abstract所修饰。静态的方法中没有this和super关键字，因为它们与具体对象关联**。
```java
// Illegal combination of modifiers: 'abstract' and 'static'
public abstract static void test();
// 'this' cannot be referenced from a static context
// 'super' cannot be referenced from a static context
public static void change() throws CloneNotSupportedException {
    this.clone();
    super.clone();
}
```

### 2.3、修饰代码块
- **被static修饰的普通代码块为静态代码块，静态代码块中不可以有静态变量、静态方法**。
- **格式**：
  ```java
  static{
      // Modifier 'static' not allowed here
      static int i = 0;
  }
  ```
- **特点**：随着类的加载而加载，只加载一次，先于主方法、构造代码块执行。

### 2.4、修饰内部类
　　非静态内部类依赖于外部类的实例，也就是说需要先创建外部类实例，才能用这个实例去创建非静态内部类。而静态内部类不需要。
```java
public class OuterClass {
    class InnerClass {
    }

    static class StaticInnerClass {
    }

    public static void main(String[] args) {
        // InnerClass innerClass = new InnerClass(); // 'OuterClass.this' cannot be referenced from a static context
        OuterClass outerClass = new OuterClass();
        InnerClass innerClass = outerClass.new InnerClass();
        StaticInnerClass staticInnerClass = new StaticInnerClass();
    }
}
```

### 2.5、静态导包
　　在使用静态变量和方法时不用再指明 ClassName，从而简化代码，但可读性大大降低。
```java
import static com.xxx.ClassName.*
```


八、继承、抽象、多态
=================

## 1、继承

### 1.1、概述
　　在现实生活中，继承一般指的是子女继承父辈的财产。在程序中，继承描述的是事物之间的所属关系，通过继承可以使多种事物之间形成一种关系体系。

　　**Java中的继承描述的是类与类之间的所属关系，只有当一个类是属于另一个类的一种时，满足is a关系时，才能使用继承，不能为了继承而继承**。

### 1.2、格式
```java
class 子类 extends 父类 {
}
```

### 1.3、继承的特点
- **只支持单一继承，一个类只能有一个直接父类**。
  ```java
  class A {}
  class B {}
  class C extends A, B {} // Class cannot extend multiple classes
  ```

- **支持多层继承**。
  ```java
  class A {}
  class B extends A {}
  class C extends B {}
  ```

- **一个类可以被多个类同时继承**。
  ```java
  class A {}
  class B extends A {}
  class C extends A {}
  ```

### 1.4、继承中成员的特点
- **子类只能继承父类非私有的成员**
- **使用时遵循的是就近原则**
- **如果子类重写父类中的方法就调用子类的方法**

### 1.5、继承的利弊
- **利**：提高了代码的复用性和可维护性；使类与类之间产生了关联关系，形成继承体系；是多态的前提之一。

- **弊**：类与类之间的耦合性增强了。

### 1.6、this和super
- **this**：**当前对象的引用**。

  　　当局部变量和成员变量同名时，通过this.的方式来区分这是成员变量；可以调用本类的成员变量和成员方法；可以在本类的构造方法中，调用其他的构造方法。

- **super**：**子类对象的父类引用**。

  　　可以在子类中，调用父类的非私有成员变量和成员方法；可以在子类的构造方法中，调用父类的构造方法。

### 1.7、初始化顺序
　　静态变量和静态语句块优先于实例变量和普通语句块，静态变量和静态语句块的初始化顺序取决于它们在代码中的顺序。最后才是构造函数的初始化。

- 父类（静态变量、静态语句块）
- 子类（静态变量、静态语句块）
- 父类（实例变量、普通语句块）
- 父类（构造函数）
- 子类（实例变量、普通语句块）
- 子类（构造函数）

## 2、抽象
　　**分析事物时，发现了共性内容，就出现向上抽象**。

### 2.1、抽象类
#### 2.1.1、概述
　　不具体，抽象类一般都是父类，子类的共性内容向上抽取得来，但是子类的方法可以描述具体的功能，而父类中共性的方法不能明确具体的功能。

#### 2.1.2、格式
```java
abstract class A {
    // 不能使用private、static、final修饰
    public abstract void method();
}
```

#### 2.1.3、特点
- **抽象类和抽象方法都使用 abstract 关键字进行声明**。
- **抽象方法只能在抽象类里面，抽象类中可以有非抽象的方法**。
- **抽象类不能被实例化，只能被继承**。
- **一个类继承了抽象类要么重写所有的抽象方法，要么他自己是抽象类**。

#### 2.1.4、abstract关键字不能和哪些关键字共存
- **final**

　　因为abstract修饰的方法是抽象方法，都得被重写才有意义，而final修饰的方法确是不能被重写的，冲突了，它们不能共存

- **private**

　　因为abstract修饰的方法是抽象方法，都得被重写才有意义，而private修饰的方法不能被重写，冲突了，它们不能共存

- **static**

　　因为abstract修饰是没有方法体的，static修饰的方法可以直接类名.的方式调用，直接调用没有方法体的方法没有意义

### 2.2、接口
　　**接口是功能的集合，同样可看做是一种数据类型，是比抽象类更为抽象的“类”**。
#### 2.2.1、概述
　　接口只描述所应该具备的方法，并没有具体实现，具体的实现由接口的实现类(相当于接口的子类)来完成。这样将功能的定义与实现分离，优化了程序设计。

　　接口是抽象类的延伸，在 Java 8 之前，它可以看成是一个完全抽象的类，也就是说它不能有任何的方法实现。

　　从 Java 8 开始，接口也可以拥有默认的方法实现，这是因为不支持默认方法的接口的维护成本太高了。在 Java 8 之前，如果一个接口想要添加新的方法，那么要修改所有实现了该接口的类，让它们都实现新增的方法。

#### 2.2.2、格式
```java
interface A {}
interface B {}
interface C extends A, B {}
class D implements A, B {}
```

#### 2.2.3、特点
- **常量的默认修饰符为：public static final**
- **抽象方法的默认修饰符为：public abstract**
- **接口不能实例化（不能直接创建对象）**

#### 2.2.4、优点
- **打破了继承的局限性**
- **对外提供规则**
- **降低了程序的耦合性**

#### 2.2.5、接口和类的关系
- **类与类**：单继承，多层继承
- **类与接口**：类只能实现接口，多实现
- **接口与接口**：接口只能继承接口，多继承

### 2.3、接口与抽象类的区别
#### 2.3.1、共性
　　**不断的进行抽取，抽取出抽象的，没有具体实现的方法,都不能实例化（不能创建对象）**。

#### 2.3.2、区别
- **设计上**：

　　抽象类提供了一种 IS-A 关系，需要满足里式替换原则，即子类对象必须能够替换掉所有父类对象。而接口更像是一种 LIKE-A 关系，它只是提供一种方法实现契约，并不要求接口和实现接口的类具有 IS-A 关系。

- **与类的关系**：

接口与类只能是实现关系，可以多实现。抽象类与类只能是继承关系，并只能单一继承，可以有多层继承。

- **成员**：

　　接口的成员只能是 public 的，而抽象类的成员可以有多种访问权限。接口的成员变量只能是 public static final 修饰的，而抽象类的成员变量没有这种限制。

## 3、多态
### 3.1、概述
　　**一种事物的多种形态，Java中的多态体现在父类的引用指向子类**。

### 3.2、格式
```java
class Animal {}
class Dog extends Animal {}
Animal a = new Dog();
```

### 3.3、多态前提
- **有继承或者实现关系**
- **有方法重写**
- **父类引用指向子类对象**

### 3.4、多态下成员调用的特点
- **成员变量**：编译看左边（父类），运行看左边（父类）
- **普通方法**：编译看左边（父类），运行看右边（子类）
- **静态方法**：编译看左边（父类），运行看左边（父类）

　　**总结：编译时期都是看父类中是否有对应的成员变量、普通方法、静态方法，没有则编译报错。运行时具体调用则是除普通方法是调用子类实现外，成员变量和静态方法调用的都是父类的实现**。

### 3.5、多态下的类型转换
- **向上转型**：当有子类对象赋值给一个父类引用时，便是向上转型，多态本身就是向上转型的过程。
```java
Animal a = new Dog();
```

- **向下转型**：一个已经向上转型的子类对象可以使用强制类型转换的格式，将父类引用转为子类引用，这个过程是向下转型。如果是直接创建父类对象，是无法向下转型的。
```java
Dog d = (Dog) a;
```

### 3.6、多态优缺点
- **优点**：提高代码的可维护性、可扩展性
- **缺点**：无法调用子类的特有功能（比如成员变量、静态方法）


九、反射
=================

## 1、概述
　　**在运行时期，可以获取和调用类的所有的构造方法、成员变量和成员方法**。

　　反射是Java中解剖学，可以对类进行解剖，首先要获取类的字节码对象，然后获取其中的构造方法、成员变量和成员方法。

## 2、字节码对象
- 对象.getClass();
```java
Animal a = new Animal();
Class clazz = a.getClass();
```

- 类名.class;
```java
Class clazz = Animal.class;
```

- Class.forName(全类名);
```java
Class clazz = Class.forName("com.xxx.Animal")
```

## 3、Class类
### 3.1、反射操作构造方法
```java
// 获取指定参数的public修饰的构造方法，如果不传递参数就是获取空参构造
public Constructor<T> getConstructor(Class<?>... parameterTypes) {}

// 获取所有的public修饰的构造方法
public Constructor<?>[] getConstructors() throws SecurityException {}

// 通过空参构造创建对象
public T newInstance() throws InstantiationException, IllegalAccessException {}
```

### 3.2、反射操作成员变量
- **公有**：
  ```java
  // 获取所有公有的成员变量
  public Field[] getFields() throws SecurityException {}

  // 获取指定的公有的成员变量
  public Field getField(String name) throws NoSuchFieldException, SecurityException {}
  ```

- **私有**：
  ```java
  // 获取所有的成员变量，包括私有的
  public Field[] getDeclaredFields() throws SecurityException {}

  // 获取指定的成员变量，包括私有的
  public Field getDeclaredField(String name) throws NoSuchFieldException, SecurityException {}
  ```

### 3.3、反射获取成员方法
- **公有**：
  ```java
  // 获取所有的公有的成员方法
  public Method[] getMethods() throws SecurityException {}

  // 获取指定的公有的成员方法，第一个参数是方法名，方法参数类型的字节码对象
  public Method getMethod(String name, Class<?>... parameterTypes) throws NoSuchMethodException, SecurityException {}
  ```

- **私有**：
  ```java
  // 获取所有的成员方法，包括私有的
  public Method[] getDeclaredMethods() throws SecurityException {}

  // 获取指定的成员方法，包括私有的，当方法没有参数列表时，第二参数可以不传递
  public Method getDeclaredMethod(String name, Class<?>... parameterTypes) throws NoSuchMethodException, SecurityException {}
  ```

## 4、反射的优点  

- **可扩展性**：

　　应用程序可以利用全限定名创建可扩展对象的实例，来使用来自外部的用户自定义类。

- **类浏览器和可视化开发环境**：

　　一个类浏览器需要可以枚举类的成员。可视化开发环境（如 IDE）可以从利用反射中可用的类型信息中受益，以帮助程序员编写正确的代码。

- **调试器和测试工具**：

　　调试器需要能够检查一个类里的私有成员。测试工具可以利用反射来自动地调用类里定义的可被发现的 API 定义，以确保一组测试中有较高的代码覆盖率。

## 5、反射的缺点
　　尽管反射非常强大，但也不能滥用。如果一个功能可以不用反射完成，那么最好就不用。在我们使用反射技术时，下面几条内容应该牢记于心。

- **性能开销**：

　　反射涉及了动态类型的解析，所以 JVM 无法对这些代码进行优化。因此，反射操作的效率要比那些非反射操作低得多。我们应该避免在经常被执行的代码或对性能要求很高的程序中使用反射。

- **安全限制**：

　　使用反射技术要求程序必须在一个没有安全限制的环境中运行。如果一个程序必须在有安全限制的环境中运行，如 Applet，那么这就是个问题了。

- **内部暴露**：

　　由于反射允许代码执行一些在正常情况下不被允许的操作（比如访问私有的属性和方法），所以使用反射可能会导致意料之外的副作用，这可能导致代码功能失调并破坏可移植性。反射代码破坏了抽象性，因此当平台发生改变的时候，代码的行为就有可能也随着变化。

- [Trail: The Reflection API](https://docs.oracle.com/javase/tutorial/reflect/index.html)
- [深入解析 Java 反射（1）- 基础](http://www.sczyh30.com/posts/Java/java-reflection-1/)


十、泛型
=================

## 1、概述
　　是一种广泛的类型，把明确数据类型的工作提前到了编译时期，借鉴了数组的特点。

　　JDK1.5 开始增加的新特性，解决了类型转换不方便或异常问题。

## 2、优点
- **是一种安全机制，避免了类型转换异常，将运行时可能出现的问题提前到了编译时期解决**
- **省去了强转的操作**
- **可以简化我们代码的书写**

## 3、限定通配符
　　对类型进行了限制，有如下两种：
- **< ? extends T>**：它通过确保类型必须是T的子类来设定类型的上界。

- **< ? super T>**：它通过确保类型必须是T的父类来设定类型的下界。

## 4、非限定通配符
**<?>**：可以用任意类型来代替

- [10 道 Java 泛型面试题](https://cloud.tencent.com/developer/article/1033693)


十一、异常
=================

## 1、概述
　　不正常，程序在编译或者运行时出现的错误就是异常。

　　在Java中，把异常信息封装成了一个类。当出现了问题时，就会创建异常类对象并抛出异常相关的信息（如异常出现的位置、原因等），使用Exception类来描述异常。

## 2、异常体系
```
Throwable
	|-Error：严重的错误，程序无法处理的，比如服务器宕机，数据库崩溃，内存溢出
	|-Exception：非严重的错误，可以处理的
		|—编译时异常：Exception下所有的除了RuntimeException及其子类之外的所有的异常
		|—运行时异常：Exception下包含RuntimeException及其子类
```

## 3、处理异常
### 3.1、默认抛出(throws)
　　throws用于抛出异常类名，使用在方法声明上；throws可以抛出多个异常，多个之间用逗号分隔。

- **格式**：
```java
修饰符 返回值类型 方法名(参数列表) throws 异常类名{}
```

### 3.2、捕获异常(try...catch...)
　　catch块可以没有，也可以有多个；多个catch块最多只会执行一个，异常必须按照从小到大排列。finally表示最终，一定会执行的语句块，常常用于释放资源。

- **格式**：
```java
  try {

  } catch (异常类型 变量名) {

  } finally {

  }
  ```

- **finally不执行原因**：
  - 当有退出JVM的语句时：System.exit(0);
  - finally代码块中有异常时

## 4、throw和throws的区别
- throws它是异常处理的方式之一，在方法声明上面使用，抛出的是异常类名，可以抛出多个，多个之间用逗号隔开。
- throw它是制造异常的方式，在方法内部使用，抛出的是异常对象，一个throw只能抛出一个异常对象。

## 5、自定义异常
　　自定义一个类继承Exception或者RuntimeException即可。
```java
public class MallException extends Exception {

    private String code;
    private String msg;
    private Object data;
    private ExceptionEnum exceptionEnum;

    public MallException() {
    }

    public MallException(ExceptionEnum exceptionEnum) {
        this.code = exceptionEnum.getCode();
        this.msg = exceptionEnum.getMsg();
        this.exceptionEnum = exceptionEnum;
    }
}
```


十二、Object 通用方法
=================

## 1、概览
　　**Object类是Java语言中的根类，即所有类的父类**。它描述的所有方法子类都可以使用。

```java
public final native Class<?> getClass();

public native int hashCode();

public boolean equals(Object obj) {
    return (this == obj);
}

protected native Object clone() throws CloneNotSupportedException;

public String toString() {
    return getClass().getName() + "@" + Integer.toHexString(hashCode());
}

public final native void notify();

public final native void notifyAll();

public final native void wait(long timeout) throws InterruptedException;

protected void finalize() throws Throwable { }
```

## 2、hashCode()
　　hashCode() 返回哈希值

　　HashSet 和 HashMap 等集合类使用了 hashCode() 方法来计算对象应该存储的位置，因此要将对象添加到这些集合类中，需要让对应的类实现 hashCode() 方法。

```java
public int hashCode() {
    int result = 1;
    Object name = this.getName();
    result = result * 59 + (name == null ? 43 : name.hashCode());
    Object age = this.getAge();
    result = result * 59 + (age == null ? 43 : age.hashCode());
    return result;
}
```

## 3、equals()
　　equals() 是用来判断两个对象是否等价。等价的两个对象散列值一定相同，但是散列值相同的两个对象不一定等价，这是因为计算哈希值具有随机性，两个值不同的对象可能计算出相同的哈希值。

　　两个对象具有等价关系，需要满足以下五个条件：
- **自反性**
```java
x.equals(x); // true
```

- **对称性**
```java
x.equals(y) == y.equals(x); // true
```

- **传递性**
```java
if (x.equals(y) && y.equals(z))
    x.equals(z); // true;
```

- **一致性**
多次调用 equals() 方法结果不变
```java
x.equals(y) == x.equals(y); // true
```

- **与 null 的比较**
对任何不是 null 的对象 x 调用 x.equals(null) 结果都为 false
```java
x.equals(null); // false;
```

　　**在覆盖 equals() 方法时应当总是覆盖 hashCode() 方法，保证等价的两个对象哈希值也相等**。
```java
public boolean equals(final Object o) {
    if (o == this) {
        return true;
    } else if (!(o instanceof User)) {
        return false;
    } else {
        User other = (User)o;
        if (!other.canEqual(this)) {
            return false;
        } else {
            Object thisName = this.getName();
            Object otherName = other.getName();
            if (thisName == null) {
                return otherName == null;
            } else if (!thisName.equals(otherName)) {
                return false;
            }

            Object thisAge = this.getAge();
            Object otherAge = other.getAge();
            if (thisAge == null) {
                return otherAge == null;
            } else return thisAge.equals(otherAge);
        }
    }
}

protected boolean canEqual(final Object other) {
    return other instanceof User;
}
```

## 4、clone()
　　clone() 可见范围是 protected 的 Object 方法，一个类不显式去重写 clone()，其它类就不能直接去调用该类实例的 clone() 方法。所以实体类使用克隆的前提是：
- **实现Cloneable接口，这是一个标记接口，自身没有方法**
- **覆盖clone()方法，可见性提升为public**

```java
public class Cert {

    private int no;

    public Cert(int no) {
        this.no = no;
    }
}

public class User implements Cloneable {

    private String name;
    private Integer age;
    private Cert cert;

    @Override
    protected Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}
```

### 4.1、浅拷贝
　　**被复制对象的所有值属性都含有与原来对象的相同，而所有的对象引用属性仍然指向原来的对象**。
```java
public static void main(String[] args) throws CloneNotSupportedException {
    User user = new User();
    user.setName("张三");
    user.setAge(28);
    user.setCert(new Cert(1));
    User clone = (User) user.clone();

    System.out.println(user == clone); // false
    System.out.println(user.getName().equals(clone.getName())); // true
    System.out.println(user.getAge().equals(clone.getAge())); // true
    System.out.println(user.getCert() == clone.getCert()); // true
    user.getCert().setNo(2);
    System.out.println(clone.getCert().getNo()); // 2
}
```

### 4.2、深拷贝
　　**在浅拷贝的基础上，所有引用其他对象的变量也进行了clone，并指向被复制过的新对象**。
```java
public class Cert implements Cloneable {

    private int no;

    @Override
    protected Object clone() throws CloneNotSupportedException {
        return super.clone();
    }
}

public class User implements Cloneable {
    @Override
    public Object clone() throws CloneNotSupportedException {
        User user = (User)super.clone();
        Cert cert = (Cert)user.getCert().clone();
        user.setCert(cert);
        return user;
    }
}

public static void main(String[] args) throws CloneNotSupportedException {
    User user = new User();
    user.setName("张三");
    user.setAge(28);
    user.setCert(new Cert(1));
    User clone = (User) user.clone();

    System.out.println(user == clone); // false
    System.out.println(user.getName().equals(clone.getName())); // true
    System.out.println(user.getAge().equals(clone.getAge())); // true
    System.out.println(user.getCert() == clone.getCert()); // false
    user.getCert().setNo(2);
    System.out.println(clone.getCert().getNo()); // 1
}
```

### 4.3、clone()的替代方案
　　使用 clone() 方法来拷贝一个对象即复杂又有风险，它会抛出异常，并且还需要类型转换。Effective Java 书上讲到，最好不要去使用 clone()，可以使用拷贝构造函数或者拷贝工厂来拷贝一个对象。
```java
public HashMap(Map<? extends K, ? extends V> m) {
    this.loadFactor = DEFAULT_LOAD_FACTOR;
    putMapEntries(m, false);
}
```

## 5、toString()
　　将对象转为字符串，全类名@内存地址值的十六进制表现形式。该方法一般情况下都会被重写，重写完之后一般用于显示对象中成员变量的值。
```java
public String toString() {
    return "User(name=" + this.getName() + ", age=" + this.getAge() + ")";
}
```

## 6、notify()

## 7、wait()

## 8、finalize()

十三、注解
=================

# 参考资料
- https://github.com/CyC2018/CS-Notes/blob/master/notes/Java%20%E5%9F%BA%E7%A1%80.md
