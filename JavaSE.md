

# java前奏

`java运行机制简单说明`

![image-20250628210320894](D:\01\技术\感获\md文档\JavaSE.assets\image-20250628210320894.png)

javac命令编译工具编译.java文件为.class文件，随后通过相应JVM运行



已知java命令

```
javac	编译
java	执行 .class文件
	// java Tst
	// java设计者认为这样就是运行一个Test类，不需要加后缀，加上了反而是运行了一个名为Test.class的类	
javap	反（向）编译
```



 java编写的代码编译后不能直接被机器执行，需要解释器，所以java是解释型语言

 因为不同机器能识别并执行的机器码不同，为了沟通，解释型语言编译后生成中间字节码（与硬件无关），由解释器将字节码转换为对应机器码。（这中间字节码是一种逻辑指令，不管指令具体形式如何，逻辑是不变的）



![image-20250628211649880](D:\01\技术\感获\md文档\JavaSE.assets\image-20250628211649880.png)







java**转义字符**

![image-20250629112116578](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629112116578.png)

\t适合用来打表	代表tab功能键

\r\n在现代终端中实现效果一样，但本质不一样

比如win用\n换行，unix用\r，如果unix下文本拿到win下，就会混成一团

\r是return功能键，意思是回到行首

```
\r使用实例
进度条
进度变化，则用\r覆盖原内容相应部分，实现相应进度条走动效果

“sss/raa"
最后输出aas
```



javadoc **标签**

```bash
cmd命令
javadoc -d xxx -author -version src/Main.java
```

解释：

- -d xxx:生成doc文档到指定位置 没有会自动创建
- `-author` ：生成文档时包含 `@author` 信息。
- `-version` ：生成文档时包含 `@version` 信息。
- `src/Main.java` ：指定要处理的源文件路径（为谁生成文档）

执行完命令后，指定位置生成 Javadoc 文档，打开 `index.html` 就能查看。

如果类以后定义了包（比如 `package com.example;` ），目录结构变成 `src/com/example/Main.java` 这种符合包结构的形式，那么命令可以调整为：

```bash
javadoc -d doc -author -version -sourcepath src com.example
```

这里 `-sourcepath src` 指定源文件所在的根路径，`com.example` 是包名，这样就能为包下的类正确生成文档。



可以指定编码避免乱码问题

```cmd
javadoc -d doc -author -version -encoding UTF-8 -charset UTF-8 src/Main.java
```





文档注释

/**

​	*

​	*

*/

文档标签

@author等







# java变量



```java
// + 两方均为数值，做加法运算、有一方是字符串则拼接
System.out.println(100+98);
System.out.println("100"+98);
System.out.println(100+98 + "hello");
System.out.println("hello" + 100 + 98);


198
10098
198hello
hello10098
```



# java数据类型



## 整型

![image-20250629125611025](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629125611025.png)

为保证java的移植性，所有数据类型都有固定大小，以此不受系统影响

## 浮点型

java浮点型默认为double

```java
//科学计数法也行
float num = (float) 2.21e2;
```



浮点数的精度误差问题，比如2.1在机器中存储是2.100000000000000001

```java
//控制精度计算
a = 2.1
b = 2.10000000000000001

# 保留两位小数后比较
rounded_a = round(a, 2)
rounded_b = round(b, 2)
print(rounded_a == rounded_b)  # 输出 True
```

```java
// 使用BigDecimal
import java.math.BigDecimal;

public class Main {
    public static void main(String[] args) {
        BigDecimal a = new BigDecimal("2.1");
        BigDecimal b = new BigDecimal("2.10000000000000001");
        
        // 比较
        int compareResult = a.compareTo(b);
        System.out.println(compareResult == 0);  // 输出 False（精确比较）
        
        // 加法示例
        BigDecimal result = a.add(b);
        System.out.println(result);  // 输出 4.20000000000000001（精确结果）
    }
}
```



## 字符型

java中字符本质是整数，所以字符可以进行整数运算

![image-20250629155622616](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629155622616.png)





字符可以存储常量整型，但变量整型不行（必须强制转换）

```java
int n1 = 65;
char c1 = (char)n1;
```

这涉及编译期检查和运行时行为

编译器能在编译时直接确认常量的值是否在 `char` 范围内（`0 ~ 65535`）以确保合法，避免运行时额外操作

变量值运行时才能确定，而编译期先于运行期，编译器会先接触到变量，并按规则系统要求变量强制转换







转义字符本身就是字符

只不过它存储的字符具有特定功能





## 布尔型

java中布尔型不能像C那样用01作为布尔值



数据类型中精度低的自动转向精度高的

![image-20250629161205710](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629161205710.png)

char占1字节，short占2字节，char却直接转int，是因为char是字符型，虽然本质是整型，但又因为字符不需要±符号，所以是无符号型，这就导致实际上char精度比short精度大

所以图中有两条分支



多数据类型混合运算，bool不参与，精度小隐式转换为精度大的

byte、short、char参与运算时，隐式转为int型，也就是说运算最小精度是整型精度





## String

String转其它类型，其它类型转String，保证转换的数据合法，调用相关方法即可



这些方法是怎么实现的？

















## 强制转换

强制转换就是直接砍掉高位，不考虑什么四舍五入的规则

```java
比如

int i = (int)1.999;
System.out.println(i);

// 结果1
```





**JavaAPI**

![image-20250629132147105](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629132147105.png)





# **运算符**

++（可以同理推--）

```java
int a = 1;
int b = 2;
a = b++;
System.out.println(a+" "+b);
//结果2 3

int i = 1;
i = i++;
System.out.println(i);
//结果1,而非2
我以前理解错了，但是结果却对了，导致我一直以为我理解的是对的
正确理解需要注意：子表达式的结果会被临时存储
赋给变量的是子表达式的值
```

## 关系运算符

![image-20250629190125335](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629190125335.png)

```java
在 Java 中，如果一个类实现了某个接口或继承了某个抽象类，那么该类的对象可以被视为该接口或抽象类的实例。

public class Main {
    public static void main(String[] args) {

        Bird bird = new Bird();
        Dog dog = new Dog();
        boolean ha = dog instanceof asd;
        System.out.println(ha);
    }

    static abstract class Animal{};

    static class Bird extends Animal{
        private int name;
    };

    static interface asd{};

    static class Dog implements asd {};

}	
```



## 逻辑运算符

&&

第1个假直接假

||

第1个真直接真

效率更高



&

|

除了作逻辑运算符，还是位运算符

需要强制计算两侧表达式时使用（如位运算或调试）



^逻辑异或

相同false，不同true





## 运算符优先级

| 优先级 | 运算符                                                       | 结合性      | 说明                                          |                      |                  |
| ------ | ------------------------------------------------------------ | ----------- | --------------------------------------------- | -------------------- | ---------------- |
| 1      | `.`、`()`、`{}`、`;`、`,`                                    | -           | 成员访问、方法调用等                          |                      |                  |
| 2      | `++`（后缀）、`--`（后缀）                                   | L→R         | 后缀自增 / 自减                               |                      |                  |
| 3      | `++`（前缀）、`--`（前缀）、`~`、`!`、`(类型)`               | R→L         | 前缀自增 / 自减、按位非、逻辑非、强制类型转换 |                      |                  |
| 4      | `*`、`/`、`%`                                                | L→R         | 乘、除、取模                                  |                      |                  |
| 5      | `+`（算术加）、`-`（算术减）                                 | L→R         | 加法、减法                                    |                      |                  |
| 6      | `<<`、`>>`、`>>>`                                            | L→R         | 左移、带符号右移、无符号右移                  |                      |                  |
| 7      | `<`、`>`、`<=`、`>=`、`instanceof`                           | L→R         | 关系比较、类型判断                            |                      |                  |
| 8      | `==`、`!=`                                                   | L→R         | 相等、不相等判断                              |                      |                  |
| 9      | `&`（按位与）                                                | L→R         | 按位与运算                                    |                      |                  |
| 10     | `^`                                                          | L→R         | 按位异或                                      |                      |                  |
| 11     | `                                                            | `（按位或） | L→R                                           | 按位或运算           |                  |
| 12     | `&&`                                                         | L→R         | 短路与（逻辑与）                              |                      |                  |
| 13     | `                                                            |             | `                                             | L→R                  | 短路或（逻辑或） |
| 14     | `? :`                                                        | R→L         | 三元条件运算符                                |                      |                  |
| 15     | `=`、`*=`、`/=`、`%=`、`+=`、`-=`、`<<=`、`>>=`、`>>>=`、`&=`、`^=`、` | =`          | R→L                                           | 赋值及复合赋值运算符 |                  |





**命名规则规范**

规则是必须遵守的，规范是大家共同制定的，现在也是必须遵守的

[alibaba/p3c: Alibaba Java Coding Guidelines pmd implements and IDE plugin](https://github.com/alibaba/p3c)









java**关键字保留字**

![image-20250629203846548](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629203846548.png)

![image-20250629203850812](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629203850812.png)

![image-20250629203853769](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629203853769.png)





位运算

~按位取反









































