# Java_Learning 记录学习Java过程

## Java学习 [Day1 2023/10/31](https://www.bilibili.com/video/BV1PY411e7J6?p=14&vd_source=33207922e975d5ad1770261da92cead1)
## <font face="宋体">命令行执行Java文件<font size=4>
>1. 编写：将源码写入.java后缀文件
>2. 编译：首先用javac 文件名.java 生成类名.class的字节码文件；
>3. 运行：其次用java 字节码文件（无后缀）,运行出结果
```java
class helloworld{
	public static void main(String[] args){
		System.out.println("hello, world");
}
}
```