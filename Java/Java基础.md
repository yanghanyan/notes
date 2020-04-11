<!-- GFM-TOC -->
- [一、Java概述](#--java--)
  * [1、Java语言发展史](#1-java-----)
  * [2、JVM,JRE,JDK的概述](#2-jvm-jre-jdk---)
    + [2.1、什么是跨平台?](#21--------)
    + [2.2、JVM JRE JDK](#22-jvm-jre-jdk)
- [二、数据类型](#------)
  * [1、基本数据类型](#1-------)
  * [2、包装类型](#2-----)
  * [3、数据类型转换](#3-------)
    + [3.1、隐式转换](#31-----)
    + [3.2、强制转换](#32-----)
  * [4、缓存池](#4----)
- [三、String](#--string)
  * [1、概览](#1---)
  * [2、不可变的好处](#2-------)
    + [2.1、可以缓存 hash 值](#21------hash--)
    + [2.2、String Pool 的需要](#22-string-pool----)
    + [2.3、安全性](#23----)
    + [2.4、线程安全](#24-----)
  * [3、String, StringBuffer and StringBuilder](#3-string--stringbuffer-and-stringbuilder)
    + [3.1、可变性](#31----)
    + [3.2、线程安全](#32-----)
  * [4、String Pool](#4-string-pool)
  * [5、new String("abc")](#5-new-string--abc--)
- [四、运算符](#-----)
  * [1、算数运算符](#1------)
  * [2、移位运算符](#2------)
    + [2.1、左移运算符（<<）](#21----------)
    + [2.2、有符号右移运算符（>>）](#22-------------)
    + [2.3、无符号右移运算符（>>>）](#23--------------)
  * [3、赋值运算符](#3------)
  * [4、关系运算符](#4------)
  * [5、逻辑运算符](#5------)
  * [6、三元运算符](#6------)
  * [7、位运算符](#7-----)
    + [7.1、&（与位运算）](#71--------)
    + [7.2、|（或位运算）](#72--------)
    + [7.3、~（非位运算）](#73--------)
    + [7.4、^（异或位运算）](#74---------)
- [五、流程控制语句](#--------)
  * [1、选择流程控制语句](#1---------)
    + [1.1、if](#11-if)
    + [1.2、switch](#12-switch)
  * [2、循环流程控制语句](#2---------)
    + [2.1、for](#21-for)
    + [2.2、while](#22-while)
    + [2.3、do ... while](#23-do--while)
    + [2.4、三种循环区别](#24-------)
  * [3、控制循环语句](#3-------)
- [六、方法（函数）](#--------)
  * [1、方法中参数传递](#1--------)
  * [2、重写(Override)](#2----override-)
  * [3、重载(Overload)](#3----overload-)
- [七、关键字](#-----)
  * [1、final](#1-final)
    + [1.1、修饰变量](#11-----)
    + [1.2、修饰方法](#12-----)
    + [1.3、修饰类](#13----)
  * [2、static](#2-static)
    + [2.1、修饰变量](#21-----)
    + [2.2、修饰方法](#22-----)
    + [2.3、修饰代码块](#23------)
    + [2.4、修饰内部类](#24------)
    + [2.5、静态导包](#25-----)
    + [2.6、初始化顺序](#26------)
- [参考资料](#----)
<!-- GFM-TOC -->

一、Java概述
=================

## 1、Java语言发展史
　　詹姆斯·高斯林（James Gosling）1977年获得了加拿大卡尔加里大学计算机科学学士学位，1983年获得了美国卡内基梅隆大学计算机科学博士学位，毕业后到IBM工作，设计IBM第一代工作站NeWS系统，但不受重视。后来转至Sun公司，1990年，与Patrick，Naughton和Mike Sheridan等人合作“绿色计划”，后来发展一套语言叫做“Oak”，后改名为Java。

　　SUN(Stanford University Network，斯坦福大学网络公司) 

## 2、JVM,JRE,JDK的概述
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

### 2.6、初始化顺序
　　静态变量和静态语句块优先于实例变量和普通语句块，静态变量和静态语句块的初始化顺序取决于它们在代码中的顺序。最后才是构造函数的初始化。

　　**存在继承的情况下，初始化顺序为**：
- 父类（静态变量、静态语句块）
- 子类（静态变量、静态语句块）
- 父类（实例变量、普通语句块）
- 父类（构造函数）
- 子类（实例变量、普通语句块）
- 子类（构造函数）

八、继承、抽象、多态
=================

## 1、继承
- **概述**：在现实生活中，继承一般指的是子女继承父辈的财产。在程序中，继承描述的是事物之间的所属关系，通过继承可以使多种事物之间形成一种关系体系。
- **格式**：
  ```java
  class 子类 extends 父类 {
  }
  ```

## 2、抽象
### 2.1、抽象类

### 2.2、接口

## 3、多态

九、反射
=================

十、泛型
=================

十一、异常
=================

十二、Object 通用方法
=================

十三、注解
=================

# 参考资料
- https://github.com/CyC2018/CS-Notes/blob/master/notes/Java%20%E5%9F%BA%E7%A1%80.md
