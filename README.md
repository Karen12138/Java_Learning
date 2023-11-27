# Java_Learning 记录学习Java过程

## Java学习 [Day1 2023/10/31](https://www.bilibili.com/video/BV1PY411e7J6?p=14&vd_source=33207922e975d5ad1770261da92cead1)

## 命令行执行Java文件<font face="宋体"><font size=4>

> 1. 编写：将源码写入.java后缀文件
>2. 编译：首先用javac 文件名.java 生成类名.class的字节码文件；
>3. 运行：其次用java 字节码文件（无后缀且注意大小写）,运行出结果

```java
/*  1. class是类，后面接着类名(建议使用驼峰命名,首字母大写)
    2. main()方法格式固定， 表示程序的入口
    public static void main(String[] args)
    3.  java程序严格区分大小写
    但源文件名强调大小写，字节码文件不区分大小写，所以程序内的类名最好不同
    4.  System.out.println();输出数据会换行
        System.out.print();输出数据不会换行
    5.  执行语句以；结尾
    6.  有多个class类编译的时候就会生成对应的相同类名的字节码文件
 */
class HelloWorld {
    public static void main(String[] args) {
        System.out.println("hello, world");
    }
}

class HelloJava {
    public static void main(String[] args) {
        System.out.println("hello, world");
    }
}

/*
        1. 如果要在class前面加上public，需要将类名和源文件名一致
        2. 一个原文件可以声明多个类，但只能有一个类被public声明
 */
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("hello, world");
    }
}
```

</font></font>

## Day2 2023/11/08

## 1. 注释类型<font face="宋体"><font size=4>

> 1. 单行注释：//
>2. 多行注释：/* ... */
>3. 文档注释（Java特有）：/** ..... */，文档注释内容可以被JDK提供的工具 javadoc 所解析，生成一套以网页文件形式体现的该程序的说明文档。
    </font></font>

## 2. 内存泄漏和内存溢出：也会在Java程序中出现

## 3. 小案例练手<font face="宋体"><font size=4>

```java
//1. 个人信息输出
class PersonInfo {
    public static void main(String[] args) {
        System.out.println("姓名：");
        System.out.println();//换行操作
        System.out.println("年龄：23");
        System.out.println("住址；上海大学");
    }
}
// 2. 换行符/n, 制表符/t(4个空格)

``` 

</font></font>

# Day3 2023/11/09 第二章 变量与运算符

## 1. 关键字<font face="宋体"><font size=4>

1. 全部都是小写字母
2. 50个关键字  
   </font></font>

## 2. 标识符：<font face="宋体"><font size=4>

&emsp;&emsp;Java中变量、方法、类名、变量名、包名、常量名等要素命名时使用的字符序列，称为标识符；  
&emsp;&emsp;技巧：凡是自己其名字的都叫标识符
> 标识符命名规则：
> + 26个英文字母、0-9、_和$
> + 数字不能开头
> + 不能使用关键字和保留字，但可以包含这些关键字和保留字
> + 标识符不能包含空格

> 标识符命名规范:
> + 包名：多单词时所有字母都小写
> + 类名、接口名：多单词的时候每个单词的首字母大写
> + 变量名、方法名：多单词的时候，第一个单词首字母小写，后面的单词首字母大写
> + 常量名：所有字母都要大写，多单词的时候要有下划线隔开  
    </font></font>

## 3. 变量<font face="宋体"><font size=4>

+ 变量概念：内存的存储区域，该区域内的数据在同一范围内不断变化

> Java变量声明的格式：数据类型 变量名 = 变量值（三要素）

+ 3.1 Java中的数据类型分类：

1. 基本数据类型（8种）

> + 整型：byte\short\int\long
> + 浮点型:float\double
> + 字符型:char
> + 布尔型:boolean

2. 引用数据类型

> + 类（class）
> + 数组（array）
> + 接口（interface）
> + 枚举（enum）
> + 注解（annnotation）
> + 记录（record）

+ 整型：byte（1个字节=8bit）\short（2个字节）\int（4个字节）\long（8个字节）

```java
class TestVariable {
    public static void main(String[] args) {
        byte b1 = 127;
        //byte b1 =128;(会超出范围)
        long l2 = 12345678l; //(声明long类型结尾需要有后缀"L/l")
        int i3 = 12345; //(大部分情况用)
        System.out.println();
    }
}
```

+ 浮点型：float(4字节)\double(8字节)

> float：单精度,声明float类型需要后缀"f/F"  
> long：双精度，通常采用double，不需要后缀

```java
class TestVariable {
    public static void main(String[] args) {
        float pi = 3.14f;
        float r1 = 1.2f;
        float r2 = 2.5f;
        int r3 = 6;
        double s;
        System.out.println();
    }
}
```

+ 字符型：char（2个字节）

> 表现形式1：使用一对'',内部有且仅有1个字符 （注意是单引号）    
> 表现形式2：直接使用 'Unicode值'来表示字符型常量：'\uXXXX'。其中，XXXX代表一个十六进制整数      
> 表现形式3：使用' 转义字符'\' '来将其后的字符转变为特殊字符型常量  
> 表现形式4：ASCII码

+ 布尔类型：boolean（true & false）常用在条件语句、循环结构等流程控制语句
  </font></font>

# Day4 2023/11/13

## 3.2 基本数据类型变量间的自动转换 <font face="宋体"><font size=4>

&emsp;&emsp;当容量小的变量和容量大的变量做运算，结果自动转换成容量大的数据类型（容量大小指的是表示数据的范围大小）

    byte、short、char--->int--->long--->float--->double

+ Tips1：byte、short、char类型之间运算结果类型是int
+ Tips2：自动提升规则不能从大到小

```java
//自动转换的特殊情况1：
class TestVariable {
    public static void main(String[] args) {
        byte b1 = 12;
        short s1 = 23;
        //编译错误
        //s1= s1 +1; s1+1是int类型不能往short转换
        //编译错误
        //short s2 = b1 + s1;
        //byte b2 = b1 + s1;
        //编译通过
        int i1 = b1 + s1;
        System.out.println(i1);
    }
}
```

</font></font>

## 3.3 强制类型转换<font face="宋体"><font size=4>

    作用：强制将容量大的数据类型转换成小容量，只需要在转换数据前加上()，括号内是要转换的数据类型；这样做会导致精度损失

```java
//数据类型强制转换：
class TestVariable {
    public static void main(String[] args) {
        double d1 = 12.3;
        //编译失败：
        //int i1 = d1;
        //强制转换，将浮点型转换成整型
        int i1 = (int) d1;
        System.out.println(i1);
    }
}
```

</font></font>

# Day5 2023/11/14

## 3.4 string类型的基本使用 <font face="宋体"><font size=4>

1. String类型基本理解

> + String属于引用数据类型，字符串
> + String类型的数据可以使用""来赋值（String是双引号，char是单引号）
> + ""内部可以有多个字符也可以没有
> + 输出结果没有""

2. 基本数据类型与String的运算

> + 基本数据类型只能与String类型做连接运算，用+表示
> + 连接符从左往右运算，若第一个数据类型遇到非字符型则不能运用连接符
> + String类型是不能利用上面3.3的()转换成基本数据类型,可以使用Integer转换
> + char类型在和基本数据类型做基本运算时要考虑转换成数值再做运算；和字符串做连接直接用单引号里面的字符

3. 二进制与多进制

```java
class BinaryTest {
    public static void main(String[] args) {
        int i1 = 123;//十进制
        int i2 = 0b01001;//二进制(0b开头)
        int i3 = 0x132f;//十六进制(0x开头)
        int i4 = 01237;//八进制(0开头)
        System.out.println(i1);//打印的结果都是十进制表示的
    }
}
```

4. 二进制的原码、反码、补码

> 1. 计算机数据的存储使用二进制`补码`形式存储，并且`最高位是符号位`
> 2. 正数的补码与反码、原码一样，称为`三码合一`
> 3. 负数的补码与反码、原码不一样：
>> - 负数的`原码`：把十进制转为二进制，然后最高位设置为1
>> - 负数的`反码`：在原码的基础上，最高位不变，其余位取反（0变1,1变0）
>> - 负数的`补码`：反码+1  
     </font></font>

# Day6 2023/11/15 <font face="宋体"><font size=4>

1.算数运算符   
Tips:取余后结果的符号和被取余的符号一致

```java
class ArithmaticTest {
    public static void main(String[] args) {
        int i1 = 2;
        int i2 = 15;
        //除法运算
        int i3 = i2 / i1;
        System.out.println(i3);
        //取余运算
        int i4 = i2 % i1;
        System.out.println(i4);
    }
}
```

a++\++a\a--\--a

```java
class ArithmaticTest {
    public static void main(String[] args) {
        //a++:先赋值后自增1
        int a1 = 2;
        int b1 = a1++;
        System.out.println("a1 = " + a1 + "b1 = " + b1);
        //++a：先自增1后赋值
        int a2 = 2;
        int b2 = ++a2;
        System.out.println("a2 = " + a2 + "b2 = " + b2);
        //a--:先赋值后自减1
        int a3 = 3;
        int b3 = a3--;
        System.out.println("a3 = " + a3 + "b3 = " + b3);
        //--a：先自减1再赋值
        int a4 = 3;
        int b4 = --a4;
        System.out.println("a4 = " + a4 + "b4 = " + b4);
        //练习1：
        int i = 1;
        int j = i++ + ++i * i++;
        System.out.println("j = " + j);//j = 10
        //练习2：
        int m = 2;
        m = m++;
        System.out.println(m);
    }
}
```

2. 赋值运算符

- 符号：=
- 扩展赋值运算符： +=、 -=、*=、 /=、%=

```java
class SetvalueTest {
    public static void main(String[] args) {
        //操作1；单个赋值
        int i1 = 10;
        int i2 = 10;
        //操作2：连续赋值
        int a, b;
        a = b = 10;
        //
        int a = 10, b = 20;
        //+= 操作
        i2 += 5;
        System.out.println();
    }
}
```

3. 比较运算符

- 比较运算符的结果都是boolean型，也就是要么是true，要么是false。

> - \>   <   >=  <= ：只适用于基本数据类型（除boolean类型之外）
> - ==   != ：适用于基本数据类型和引用数据类型

4. 逻辑运算符

- 逻辑运算符，操作的都是boolean类型的变量或常量，而且运算得结果也是boolean类型的值。

> - & 和 &&：表示"且"关系，当符号左右两边布尔值都是true时，结果才能为true。否则，为false。
> - | 和 || ：表示"或"关系，当符号两边布尔值有一边为true时，结果为true。当两边都为false时，结果为false
> - ! ：表示"非"关系，当变量布尔值为true时，结果为false。当变量布尔值为false时，结果为true。
> - ^ ：当符号左右两边布尔值不同时，结果为true。当两边布尔值相同时，结果为false。

& 和 &&的区别：
> - 如果左右两边都是true则没区别
> - 如果左边的条件是false，&还继续执行右边的操作，&&则直接不执行
> - 开发中推荐使用&&

| 和 ||的区别：
> - 如果左边是false，则都执行右边
> - 如果左边的条件是true，|还继续执行右边的操作，||则直接不执行
> - 开发中推荐使用||

5. 位运算符
6. 条件运算符：(条件表达式)? 表达式1:表达式2
   ![img.png](img.png)

> （1） 条件表达式的结果是Boolean类型   
> （2） 表达式类型是String    
> （3） 条件表达式是true则运行表达式1， false运行表达式2    
> （4） 表达式1和2需要是相同类型或兼容类型
</font></font>

# Day7 2023/11/23

## 顺序结构

## 分支结构<font face="宋体"><font size=4>

    有`if…else`和`switch-case`两种分支语句  

### 1. if-else条件判断结构

**结构1：单分支条件判断：if**

```
if(条件表达式){
    执行语句
}
```

**结构2：双分支条件判断：if...else**

```
if(条件表达式){
    执行语句1
}else{
    执行语句2}
```

**结构3：多分支条件判断：if...else if...else**

```
if (条件表达式1){
    执行语句1
} else if(条件表达式1){
    执行语句2
}
......
else if {
    执行语句n-1
} else {
    执行语句n
}
```
注意：
![img_1.png](img_1.png)
![img_2.png](img_2.png)  
> 当条件表达式之间是“`互斥`”关系时（即彼此没有交集），条件判断语句及执行语句间顺序无所谓。    
> 当条件表达式之间是“`包含`”关系时，即包含范围小的集合在上面，大的范围集合在下面。“`小上大下 / 子上父下`”，否则范围小的条件表达式将不可能被执行。


### 2. if-else嵌套
```java
/*
 * 三组数据排序
 * */
class NumberMax{
    public static void main(String[] args) {
        int num1, num2, num3;
        num1 = 25;
        num2 = 15;
        num3 = 36;
        if (num1 <= num2){
            if (num3 <= num1){
                System.out.println("三个数最小的是"+num3+"三个数最大的是"+num2);
            }else if(num3 >= num2){
                System.out.println("三个数最小的是"+num1+"三个数最大的是"+num3);
            }else{
                System.out.println("三个数最小的是"+num1+"三个数最大的是"+num2);
            }
        }else {
            if (num3 >= num1){
                System.out.println("三个数最小的是"+num2+"三个数最大的是"+num3);
            }else if(num3 <= num2){
                System.out.println("三个数最小的是"+num3+"三个数最大的是"+num1);
            }else {
                System.out.println("三个数最小的是"+num2+"三个数最大的是"+num1);
            }
        }
    }
}
```
注意：
- 语句块只有一条执行语句时，一对`{}可以省略`，但建议保留
- 当if-else结构是“多选一”时，最后的`else是可选的`，根据需要可以省略


3. switch-case选择结构
```
switch (表达式){
    case 常量1:
        执行语句1;
        break;//跳出选择结构，没有break则依次往下运行
    case 常量2:
        执行语句2;
        break;
    case 常量3:
        执行语句3;
        break;
    case 常量4:
        执行语句5;
        break;
    default:
        执行语句6;
}
```
注意：
1. switch的表达式只能有以下几种类型：byte/short/char/int, 枚举/字符串（String）
2. case子句中的值必须是常量，不能是变量名或不确定的表达式值或范围
3. default子句是可选的。同时，位置也是灵活的。当没有匹配的case时，执行default语句

</font></font>


## 循环结构<font face="宋体"><font size=4>

    有`for`、`while`、`do-while`三种循环语句
</font></font>

## Scanner：键盘输入功能的实现 <font face="宋体"><font size=4>  
- 如何从键盘获取不同类型（基本数据类型、String类型）的变量：使用Scanner类。

- 键盘输入代码的四个步骤：
    1. 导包：`import java.util.Scanner;`
    2. 创建Scanner类型的对象：`Scanner scan = new Scanner(System.in);`
    3. 调用Scanner类的相关方法（`next() / nextXxx()`），来获取指定类型的变量
    4. 释放资源：`scan.close();
    
```java
//案例：
import java.util.Scanner;
public class SecondPrimary {
    public static void main(String[] args) {
        //创建Scanner实例
        Scanner scan = new Scanner(System.in);
        //调用Scanner方法
        int age = scan.nextInt();
        double weight = scan.nextDouble();
        boolean issingle = scan.nextBoolean();
        String name = scan.next();
        System.out.println("注册的名字是"+name);
        //关闭资源
        scan.close();
    }
}
```
</font></font>

## 获取指定范围的随机数  <font face="宋体"><font size=4>  
Java的API:Math.random(随机生成[0.0,1.0)区间内的数)
```java
//随机生成[a,b]区间的随机数
class RandomTest {
    public static void main(String[] args) {
        int num1 = (int)(Math.random()*(b-a + 1) + a);
        System.out.println(num1);
    }
}
```
