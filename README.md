# Java_Learning 记录学习Java过程

## Java学习 [Day1 2023/10/31](https://www.bilibili.com/video/BV1PY411e7J6?p=14&vd_source=33207922e975d5ad1770261da92cead1)
## 命令行执行Java文件<font face="宋体"><font size=4>
>1. 编写：将源码写入.java后缀文件
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
class HelloWorld{
	public static void main(String[] args){
		System.out.println("hello, world");
}
}

class HelloJava{
    public static void main(String[] args){
        System.out.println("hello, world");
    }
}

/*
        1. 如果要在class前面加上public，需要将类名和文件名一致
        2. 一个原文件可以声明多个类，但只能有一个类被public声明
 */
public class HelloWorld{
    public static void main(String[] args){
        System.out.println("hello, world");
    }
}
```
 </font></font>

## Day2 2023/10/31
## 1. 注释类型<font face="宋体"><font size=4>
>1. 单行注释：//
>2. 多行注释：/* ... */
>3. 文档注释（Java特有）：/** ..... */，文档注释内容可以被JDK提供的工具 javadoc 所解析，生成一套以网页文件形式体现的该程序的说明文档。
    </font></font>

## 2. 内存泄漏和内存溢出：也会在Java程序中出现
## 3. 小案例练手<font face="宋体"><font size=4>
```java
//1. 个人信息输出
class PersonInfo{
    public static void main(String[] args){
        System.out.println("姓名：");
        System.out.println();//换行操作
        System.out.println("年龄：23");
        System.out.println("住址；上海大学");
    }
}
// 2. 换行符/n, 制表符/t(4个空格)

```