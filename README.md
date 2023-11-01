# Java_Learning 记录学习Java过程

## Java学习 [Day1 2023/10/31](https://www.bilibili.com/video/BV1PY411e7J6?p=14&vd_source=33207922e975d5ad1770261da92cead1)
## <font face="宋体">命令行执行Java文件<font size=4>
>1. 编写：将源码写入.java后缀文件
>2. 编译：首先用javac 文件名.java 生成类名.class的字节码文件；
>3. 运行：其次用java 字节码文件（无后缀）,运行出结果
```java
/*  1. class是类，后面接着类名
    2. main()方法格式固定， 表示程序的入口
    public static void main(String[] args)
    3.  java程序严格区分大小写
    4.  System.out.println();输出数据会换行
        System.out.println();输出数据不会换行
    5.  执行语句以；结尾
 */
public class HelloWorld{
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
```