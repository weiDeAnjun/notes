361

520



# 内存分区

不同语言内存分区不同

为什么要对内存进行分区

**原理本质**：平衡 **性能（栈快速、堆灵活 ）** 与 **开发效率（托管 vs 手动 ）**，适配语言应用场景（系统级、企业级、脚本 ）。

简单说，内存分区是 “硬件能力 + 语言需求” 共同作用的结果，不同语言根据定位（控制硬件 / 快速开发 ），选择暴露或隐藏分区细节，本质是为了高效管理内存、支撑程序运行～



| 概念         | 核心聚焦点                                          | 典型场景 / 举例                                              |
| ------------ | --------------------------------------------------- | ------------------------------------------------------------ |
| **内存结构** | 从整体视角描述内存的**组织方式、组成部分**          | 计算机系统：物理内存 + 缓存 + 虚拟内存 JVM：堆、栈、方法区等逻辑模块 |
| **内存分区** | 侧重**程序运行时的内存区域划分**（代码、栈、堆等 ） | C/C++ 进程地址空间：代码区、全局区、栈区、堆区 Java 堆内部分代（新生代、老年代 ） |
| **内存模型** | 关注**多线程 / 并发场景下的内存可见性、重排序规则** | Java 内存模型（JMM）：定义主内存、工作内存，规范线程间通信、同步规则 |

![image-20250630120457760](D:\01\技术\感获\md文档\JavaSE.assets\image-20250630120457760.png)









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

java的强制转换直接砍掉高位，不考虑什么四舍五入的规则

```java
比如

int i = (int)1.999;
System.out.println(i);

// 结果1
```



以上基本数据类型（可能还有别的）





**引用数据类型**

## 数组

数组有动态初始化和静态初始化

静态初始化，长度固定，不可伸缩扩展

![image-20250630101832168](D:\01\技术\感获\md文档\JavaSE.assets\image-20250630101832168.png)



![image-20250630101834621](D:\01\技术\感获\md文档\JavaSE.assets\image-20250630101834621.png)

数组对象 在堆中存储，数组元素 在栈或方法区（静态数组）存储

数组对象和数组元素是分开的，数组内存储的实际上是数组元素的引用（节省空间）

通过引用调用数组元素

<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250630103907885.png" alt="image-20250630103907885" style="zoom:50%;" />



1. 数组里的**元素**，若为对象类型，直接存对象引用；若为基本类型，存值但可通过 Java 特性（如自动装箱、数组对象化存储 ）融入面向对象体系。
2. 从 JVM 层面，数组对象在堆中统一以 “对象” 形式管理，有对象的元数据（类型、哈希等 ），这也是数组归为引用类型、且能参与面向对象操作（如 `instanceof` 判断 ）的根本原因。

简单说，Java 里数组整体是引用类型，元素根据自身类型，要么直接是对象，要么通过语言设计 “适配” 到对象体系，保证数组能融入 Java 面向对象的大框架～





直接数组b = 数组a,b和a的引用相同，修改谁都会影响对方，若想分开很简单，只要引用不一样就行，再把数据复制一遍就可以了

![image-20250630104405205](D:\01\技术\感获\md文档\JavaSE.assets\image-20250630104405205.png)



二维数组

![image-20250630105606494](D:\01\技术\感获\md文档\JavaSE.assets\image-20250630105606494.png)

二维数组是一维数组的组合，查找数据时，先找对应一维数组，再接着找对应数据

![image-20250630105833475](D:\01\技术\感获\md文档\JavaSE.assets\image-20250630105833475.png)

了解一下，用肯定只用第一种





```java
int[] x = {1,2,3};
System.out.println(x);

// 结果[I@1b6d3586
```

和C语言区分，C语言这样输出相当于输出x首元素

而java里：打印的是 数组对象的引用哈希码

- `[` 表示这是一个数组。
- `I` 表示数组元素类型为 `int`（`Integer` 的缩写）。
- `@` 是分隔符。
- `1b6d3586` 是数组对象的**哈希码**（通过 `x.hashCode()` 或 `System.identityHashCode(x)` 获得）。

这个哈希码是内存地址的映射，但它不是直接的物理内存地址，而是 JVM 内部维护的对象标识，可能随 GC 移动对象而变化。

在 Java 中，数组是**对象**，其内存布局包含：

1. **对象头**（Object Header）：存储哈希码、分代年龄、锁状态等元数据（通常 12 字节）。
2. **长度字段**：存储数组长度。
3. **元素数据区**：实际存储元素的内存区域。

因此，数组对象的起始地址（哈希码对应的地址）是**对象头的起始地址**，而首元素地址是对象头 + 长度字段后的偏移量（通常为 16 字节后）。

Java 刻意隐藏内存地址细节，开发者无需关心物理地址，只需通过引用操作数组。





## 类

Cat cat = new Cat();

cat是引用

成员变量 = 属性 = 字段



### 成员方法

A给方法传参，A是基本数据类型，传的是数据，A是引用数据类型，传的是引用，会改变A

<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250630131513024.png" alt="image-20250630131513024" style="zoom:50%;" />





<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250630132150322.png" alt="image-20250630132150322" style="zoom: 50%;" />

原因很简单，方法在使用时才会开辟空间，开辟后，方法的形参p也指向p1指向的空间，置空是将形参p置空，未影响p1



方法重载

重载要求方法名相同且满足（至少1项）：参数个数，参数类型，参数顺序

返回值，访问修饰符，异常的差异不能构成重载



**可变参数**

方法名称功能参数类型均相同，那无论有多少参数，也只是处理的多或少的问题，对方法无影响，因此诞生可变参数

int...取个名

因为这些参数类型相同，所以被封装到数组里了

```java
// 可变参数必须无理由放参数列表，即使接受类型不同
Fun(1, 2, 3, 6.8);


public static void Fun(int...nums,double d){};//报错
```

```java
// 可变参数可以接受0个参数
Fun(1.1f);
public static void Fun(float f, int...nums){};
```



### 构造方法

构造方法对 对象 进行初始化，创建对象时会自动调用它，二者不是同一概念，注意区分

可以有多个构造器

![image-20250701103658629](D:\01\技术\感获\md文档\JavaSE.assets\image-20250701103658629.png)



可以在构造器里用this调用其它构造器

为什么要这么做？我可能会对类进行不同的初始化，而不同的初始化也可能有相同的初始内容，为避免冗余，我直接调用，避免了冗余

```java
class T {
    String name;
    int age;

    public T(String name, int age) {
        this.name = name;
        this.age = age;
        System.out.println("T(String, int) 构造器");
    }

    public T() {
        // 重复写赋值逻辑，冗余！
        this.name = "jack";
        this.age = 100; 
        System.out.println("T() 构造器");
    }
}






class T {
    String name;
    int age;

    public T(String name, int age) {
        this.name = name;
        this.age = age;
        System.out.println("T(String, int) 构造器");
    }

    public T() {
		this("alice", 18);
        System.out.println("T() 构造器");
    }
}
```

`this(...)` 是调用**本类的其他构造器**，`super(...)` 是调用**父类的构造器**，两者都是为了复用初始化逻辑，只不过作用范围不同。

但是要注意：构造函数中只允许一次显式构造函数调用





我总觉着可以做更多，我可以在构造阶段做和类不相关的事，还可以……









类创建流程分析

![image-20250701095550081](D:\01\技术\感获\md文档\JavaSE.assets\image-20250701095550081.png)

![image-20250701095610981](D:\01\技术\感获\md文档\JavaSE.assets\image-20250701095610981.png)

JVM 首次使用类时，通过类加载器将类的字节码（.class文件）加载到方法区，存储类的元信息（如类结构、方法字节码、静态变量等）。
当执行new指令时，JVM 在堆区为对象分配内存空间，包括对象头（存储哈希码、锁状态等）和实例变量。
对象内存分配后，所有字段先初始化为默认值（如int→0，boolean→false，引用类型→null）。
显式赋值阶段：执行构造方法，按代码中的赋值语句（如int x = 10;）覆盖默认值。
若为基本数据类型（如int、char），直接存储在堆区对象内部
局部变量（如方法内的对象引用）存储在栈帧中，指向堆区对象的地址
常量区仅存储编译期确定的常量值（如final变量、字符串字面量）





没谁规定类必须被引用，因为没有引用，只能使用一次，这就是匿名类

```java
new Person().say(
```





### 作用域

局部变量(全局变量(属性)以外的变量)必须赋值才能用，否则报错，因为局部变量在方法中，方法只有调用时才会分配空间，所以其中变量没有经过初始化，没有初始值



作用域访问遵循就近原则

```java
public static class Person {
    String name = "alice";

    public void say(){
        String name = "bob";
        System.out.println(name);
    }
}

//在重名情况下，因为就近原则，输出的是bob,如想输出alice，可添加this
public static class Person {
    String name = "alice";

    public void say(){
        String name = "bob";
        System.out.println(this.Wname);
    }
}
```





```java
class Dog{
    private String name;
    private int age;
    
    public Dog(String name, int age){
        name = name;
        this = this;
    }
}

// 由于作用域就近原则，构造方法里实际上是局部变量自己又赋给自己，并没有修改类的字段
// 要用this
```





### 封装

隐藏细节，便于使用，安全

属性被private修饰，

仅提供getset方法，写在构造器里，避免通过构造器绕过封装



### 继承

某些类有很多相同字段

想在某个类基础上扩展



```java
extends	类
    
implements	接口
    
只能继承一个类    
可以继承多个接口
```



私有属性、方法不能被继承，静态方法不能被重写，但是子类可以有同名静态方法来覆盖



**对象引用，对象，类三者联系**

对象是类的实例，类是对象的模板

new是创建对象，构造器是初始化

new先于构造器，如果使用new，就必定使用构造器初始化，构造器初始化在这里是new过程的一部分

但构造器不依赖new，构造器是独立于new的，只是new的过程需要构造器



Person p = new Person();

过程是jvm:

- 在堆中分配内存空间；
- 初始化实例变量；
- 执行构造器逻辑。

p就是对象引用,指向对象在堆中地址

- 引用是栈中的变量，对象是堆中的实体；

`new`操作的本质：创建对象并返回引用





![image-20250701135506285](D:\01\技术\感获\md文档\JavaSE.assets\image-20250701135506285.png)

图片说的不明白，应该是子类必须调用父类的构造器，完成子类继承自父类的属性的初始化

谁的属性就必须用谁的构造器初始化，即使被继承了



- 子类构造器第一行隐式调用`super()`，目的是**初始化子类对象中父类的成员部分**，只是初始化，没有new，就没有创建独立的父类对象。

- 父类构造器的调用是为了初始化子类对象中的父类成员，而非创建父类实例。

子类对象的内存结构包含父类的所有成员变量（无论是否私有），但通过访问修饰符限制子类的直接访问权限。
private的核心作用是语法层面的封装，而非物理上的分离
父类的私有属性name是子类对象的一部分，随子类对象的创建而存在，不需要单独创建父类对象。访问修饰符private只是限制了类外直接访问，但不影响属性在对象内存中的存在。



子类对象的初始化流程涉及**类加载**、**父类初始化**、**子类初始化**等多个阶段

类加载检查：
若子类或父类未被加载过，先加载类（静态成员初始化）

第一次创建子类对象：
父类静态代码块        ← 父类加载，静态初始化（仅首次）
子类静态代码块        ← 子类加载，静态初始化（仅首次）
父类实例代码块        ← 父类实例初始化
父类构造器           ← 父类构造器执行
子类实例代码块        ← 子类实例初始化
子类构造器           ← 子类构造器执行

第二次创建子类对象：
父类实例代码块        ← 仅执行实例部分（静态部分不再执行）
父类构造器
子类实例代码块
子类构造器



子类继承父类，继承不仅继承父类字段，调用父类构造方法的时候，参数也会写入父类字段

```java
public static void main(String[] args)  {

    Father fa = new Father();
    System.out.println(fa.name);
    
    //输出结果是	小老虎
}


public static class GrandPa {
    String name;

    public GrandPa(String name) {
        this.name = "小老虎";
    }
}

    public static class Father extends GrandPa {
        public Father() {
            super("asd");
        }
	}

```

![image-20250701165702987](D:\01\技术\感获\md文档\JavaSE.assets\image-20250701165702987.png)

这还涉及链式查询，就是说一个属性，如果子类找不到，就去父类

![image-20250701165838571](D:\01\技术\感获\md文档\JavaSE.assets\image-20250701165838571.png)

即使字段设为子类不可访问的，子类也能找到，不过无法直接访问

若父类也没有，就一直找到object，若没有，则抛出异常







若子类继承父类属性，并对属性修改，则子类字段中父类的属性也被修改为和子类一样

```java
public class Main {

    public static void main(String[] args)  {

        Father fa = new Father();
        System.out.println(fa.name);
        fa.sout();
        //两个结果都是father
    }


    public static class GrandPa {
        String name;

        public GrandPa(String name) {
            this.name = "name";
        }

        public GrandPa(){}

    }

    public static class Father extends GrandPa {
        public Father() {
            super();
            this.name = "father";
        }

        public void sout(){
            System.out.println(super.name);
        }
    }

    public static class Son extends Father {
        String name;

        public Son(String name) {
            super();
        }
    }


}
```





因为super()和this()都要放在构造方法第1行，所以它俩不能共存于同一构造方法



java中类是单继承，不使用接口的情况下如何让java实现多继承的效果？一句话，除了爸爸还有爷爷



A继承B，B继承C，对于它们都有的属性，如何





### super

父类和子类没有重名字段，但是爷爷类有，则super访问爷爷类,若都有，遵循就近原则 



重写方法

返回值，参数列表，方法名均要相同

返回类型需要是父类返回类的子类

访问权限不能比父类小

```java
class Animal {
    public void makeSound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Cat meows");
    }
}

// 测试多态
public static void main(String[] args) {
    Animal a1 = new Dog();  // 父类引用指向子类对象
    Animal a2 = new Cat();  // 父类引用指向子类对象
    
    a1.makeSound();  // 输出：Dog barks
    a2.makeSound();  // 输出：Cat meows
}
```









### 多态



#### 上下转型

单看上下转型没有意义，要结合多态看

多态通过父类统一处理子类，很方便，但和直接用子类就是它无法直接访问子类特有方法

为此又引入下转型

(在继承那里，视角看的是子类，子类本身就拥有父类一切，但是在多态这里，父类先于子类出现，它能调用的只有和子类共有的，子类独有的它使用不了)																																																																																																																																																																																																																											



强制转换是一种语法机制，在内存的实现是：

**不改变对象在内存中的实际布局**，而是通过**修改引用的类型元信息**来改变程序对内存的解释方式

强制转换的核心在于**类型元信息的动态调整**



**类型元信息（Type Metadata）** 是描述类或对象的底层数据结构，它存储了类的定义、继承关系、方法签名等关键信息。这些元信息由 JVM 在类加载时生成，并在运行时用于类型检查、反射、动态绑定等核心机制。

每个类在 JVM 中都对应一个唯一的`java.lang.Class`对象，它存储了类的完整元信息，包括：

- 类的全限定名（如`java.util.ArrayList`）
- 直接父类的引用
- 实现的接口列表
- 字段和方法的描述符
- 访问修饰符（public/private 等）
- 静态变量和常量值

每个对象在内存中的头部包含指向其 Class 对象的指针，称为**类型指针**。

- **普通对象头**：包含哈希码、分代年龄、锁状态等。
- **数组对象头**：额外包含数组长度信息。





#### 动态绑定机制

动态机制基于多态

**动态绑定（Dynamic Binding）** 是 Java 实现多态的核心机制，它允许在**运行时**根据对象的**实际类型**来决定调用哪个方法，而非在编译时根据引用类型决定。

方法受动态机制影响，属性不会。

```java
public class Main {

    public static void main(String[] args)  {

        A a = new B();
        System.out.println(a.getI() + " ");
        //虽然调用的a的getI,但因为B类重写了该方法，所以实际调用是B的geiI方法
        

    }

    public static class A{
        int age = 30;

        public A(){

        }

        public int getI(){
            return 1 + age;
        }

    }

    public static class B extends A{
        int age = 40;

        public B(){

        }

        @Override
        public int getI(){
            return 2 + age;
        }

    }


}
```



#### 多态参数

形参是父类类型，实参允许是子类类型



#### ==和equals

![image-20250702094949819](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702094949819.png)



![image-20250702095245527](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702095245527.png)

不管形式如何花里胡哨，只要地址一样，那就是同一个



![image-20250702095331824](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702095331824.png)

equals默认和 == 功能一样，但是equals可以自定义比较内容







Object的finalize的方法

gc自动调用，或者System.gc主动调用

重写该方法，配套释放资源的操作







### 静态变量+静态变量

静态变量属于类，会被类所有对象共享

jdk7以后，在堆区，之前在方法区的静态区

static变量在类加载时就存在了



静态变量不能直接访问非静态变量

不涉及成员变量、通用方法，可以设置为静态方法

this代表类当前对象，所以静态方法中没有this、super







### 代码块

类的成员

![image-20250702162519702](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702162519702.png)

![image-20250702162814149](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702162814149.png)

静态代码块随着类加载而执行，只有这1次

代码块随着创建对象执行 



![image-20250702163200124](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702163200124.png)

![image-20250702163208022](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702163208022.png)

普通代码块new对象时，才会被调用



![image-20250702163303868](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702163303868.png)

先前还没学静态，现在又补充了，先按照定义顺序调用静态代码块和静态属性初始化，然后再是普通的，最后构造方法

![image-20250702165716741](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702165716741-1751446637620-1.png)





类的五大成员：字段、方法、构造器、代码块、内部类



### 内部类

![image-20250703084351213](D:\01\技术\感获\md文档\JavaSE.assets\image-20250703084351213.png)

内部类地位相当于局部变量，不能被权限符修饰



内部类注意3点：定义位置、作用域、本质仍是类，地位相当于局部变量



#### 局部内部类

定义在方法体、代码块内

访问外部类成员，通过	`外部类名.this.成员名`实现



#### 匿名内部类

每个类肯定都有名字以区分，匿名指的是没有用户定义得类名

匿名内部类得名称是	外部类名$数字（数字从1开始）

匿名内部类一般都是一次性的，但注意这个一次性，它不一定是单纯用了一次就释放（比如打印一条语句），也可能是完成一系列工作的这么1个动作，算是用了1次

匿名内部类只是没有用户定义的类名，不代表不能用引用指向它，不要混淆概念

接口不能实例化，使用匿名内部类会造成一种接口可以实例化的错觉

"用完就没了" 通常指**匿名对象**（如 `new A() { ... }.say()`），这种写法

```java
public class Main {

    public static void main(String[] args)  {

        A a = new A(){
            @Override
            public void say(){
                System.out.println("Hello World");
            }
        };
        a.say();	//因为有引用，匿名类没被释放，3次调用都用的同一对象
        a.say();	
        a.say();
        
    }

    
    public  interface A{
        int x = 1;

        default void say(){};

    }
}
```





#### 成员内部类

添加在外部类的成员位置

```java
Inner in = new Outter().new Inner();

Inner in = new Outter().getNewInnerInstance();	//通过方法，更方便
```











```java
public class Main {

    public static void main(String[] args)  {

        A.B b = new A().new B();
        b.say1();

    }

    
    
    public static class A{
        private String str = "asd";

        public void say(){
            System.out.println(this.str);
        }

        class B {
            private String strr;
            public void say1(){
                say();
            }
        }

        class C {
            void say2(){
            }
        }

    }
}

在类的范围内，BC都能直接访问A，因为A是它们外部类，但BC彼此不能直接访问，因为它们是同级类
外部类访问内部类需要先实例化内部类（static除外）


子类不能访问父类私有内容，因为子类只是继承，不是内部类
内部类也可以继承外部类，并使用继承操作
```



不考虑访问修饰符，静态

java类访问机制默认是越内部越隐蔽，内部类能直接访问外部类，

外部类需要通过内部类实例化才能间接访问，这又是因为，实现内部类必须依赖外部类，所以外部类想访问内部类就必须通过自己对内部类完成实例化

内部类本就可以直接访问外部类，因为它是外部类的一部分，外部类对它来说没有秘密可言

外部类本就可以直接访问内部类，但因为内部类实例化机制要求，所以不能直接访问，但其实理论上是可以直接访问的



### 枚举类

对于某些对象，如季节，天气，它们值固定且只读，用传统类体现不出来这些，用基本数据类型又不便统一，所以用枚举类

![image-20250706125121014](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706125121014.png)

```java
public class Main {

    public static void main(String[] args)  {

        System.out.println(Season.FALL.sea);
    }

    static class Season{

        public static final Season SPRING = new Season("春天", "chun");
        public static final Season SUMMER = new Season("春天", "chun");
        public static final Season FALL = new Season("春天", "chun");
        public static final Season WINTER = new Season("春天", "chun");


        String sea;
        String desc;

        private Season(String sea, String desc){
            this.sea = sea;
            this.desc = desc;
        }

        public String getSea() {
            return sea;
        }

        public String getDesc() {
            return desc;
        }
    }
}
```

也可以选择使用enum，常量对象要放在最前面

```java
enum Season{
    SPRING("春天", "春"),
    SUMMER("<夏天>", "夏"),
    AUTUMN("<秋天>", "秋"),
    WINTER("<冬天>", "冬");


    String sea;
    String desc;

    private Season(String sea, String desc){
        this.sea = sea;
        this.desc = desc;
    }

    public String getSea() {
        return sea;
    }

    public String getDesc() {
        return desc;
    }
}


//如果使用无参构造器，则可省略小括
```



枚举类本质也是类，但和普通类有很大不同：

使用`enum`关键字定义，内部默认由多个枚举常量构成，每个枚举常量本质上是该枚举类的一个实例

默认继承自`java.lang.Enum`类，并且不能再继承其他类，但可实现多个接口

构造函数只能是私有的（默认私有）

枚举常量在枚举类加载时就已经被实例化，且是全局唯一的，不能使用`new`关键字创建枚举实例

枚举类不能被继承

枚举类之间不能进行强制转换，即使是相同枚举类型的不同常量也不能进行强制转换 。

![image-20250706141704716](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706141704716.png)









### 包装类

![image-20250706180852700](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706180852700.png)

包装类实现的接口



#### 包装类和String类转换

因为实际业务经常用到，所以互转也经常它们互转也经常用到

![image-20250707152048162](D:\01\技术\感获\md文档\JavaSE.assets\image-20250707152048162.png)



![image-20250707152108686](D:\01\技术\感获\md文档\JavaSE.assets\image-20250707152108686.png)





#### 包装类常用方法

看api文档就行



![image-20250707152820975](D:\01\技术\感获\md文档\JavaSE.assets\image-20250707152820975.png)

Integer.valueOf(int)源码👇

![image-20250707152734950](D:\01\技术\感获\md文档\JavaSE.assets\image-20250707152734950.png)

如果范围是-128~127直接返回值，否则通过new的方式创建





#### 包装类、基本类型混合比较

注意包装类缓存范围-128~127

**包装类之间比较**：赋值在缓存范围则true，否则都自动通过new创建，这时候按类的比较规则比较 比较地址，结果自然false ；只要有1个通过new创建，即使在缓存范围内，也按照地址比较

**包装类和基本类比较**：包装类拆箱为基本类，基本类间比较数值，不用考虑缓存范围![image-20250707154251950](D:\01\技术\感获\md文档\JavaSE.assets\image-20250707154251950.png)



### String类

字符串是数据一种表现形式

String是java中的类，java.lang包下，用于代表和操作字符串

String重写了equals，比较内容

String类字符用unicode编码（无论字符汉字占2字节）



String是final类，不可被继承，具有**内容不可变性**

```java
String s = "abc";
// 看似修改，实际是创建新的 String 对象
s = s + "d"; 

String引用可以执行其它对象，这是引用行为，和String本身不可变性无关
这造成了Stirng内容可修改的错觉
```

通过 **私有属性 + 无修改方法 + 深拷贝构造** 共同实现的

- 具体来说：
    - `value` 是 `private`，外部无法直接访问；
    - String 类的所有方法（如 `substring`、`replace`）都返回 **新的 String 对象**，而非修改原数组；
    - 构造函数中若传入字符数组，会进行 **深拷贝**（如 `value = Arrays.copyOf(value, length)`），避免外部引用修改内部数组。



String不可继承也是避免子类破坏其不可变性

String有属性private final char value[]	就是用它存储字符串内容	同时 因为这个变量属性 是引用数据类型，又被final修饰，所以指向的地址不可修改，即永远指向同一数组对象，但这个数组里的内容可修改

<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250707170149233.png" alt="image-20250707170149233" style="zoom:50%;" />







#### String创建方式

直接赋值

new

最终都是为了使用常量值，不过new是引用类，类的属性指向值

<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250707160907482.png" alt="image-20250707160907482" style="zoom:50%;" />

不管哪种方式都先去常量池找，找到直接引用，没找到创建再引用



<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250707162357293.png" alt="image-20250707162357293" style="zoom:50%;" />





![image-20250708094219417](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708094219417.png)

编译器进行了优化，判断创建的常量池对象是否有引用指向



<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250708095821388.png" alt="image-20250708095821388" style="zoom:50%;" />

<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250708095805100.png" alt="image-20250708095805100" style="zoom:50%;" />

![image-20250708121947967](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708121947967.png)



通过对象组合，其底层使用StringBuffer的append，追加后内容不存在则在堆区生成（一般情况字符串在常量区生成，这里不是常量区，是堆区），然后指向它，然后返回的是buffer对象，C指向的是buffer



#### String常用方法

![image-20250708102146277](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708102146277.png)



![image-20250708102427446](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708102427446.png)

![image-20250708102436800](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708102436800.png)





### StringBuffer

内容可变，相较于String修改地址，效率高

扩容机制，其父类内部有个char[]作为缓冲区，默认16字节，可通过构造函数改变

适合多线程

### StringBuilder

适合单线程，因为不是线程安全的



### 常用类

![image-20250708105648603](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708105648603.png)

![image-20250708105653742](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708105653742.png)

```java
Collections.sort(personList, new Comparator<Person>() {
    @Override
    public int compare(Person p1, Person p2) {
        return p1.getAge() - p2.getAge(); // 这里返回值的正负决定排序顺序
    }
});


Collections.sort(personList, new Comparator<Person>() {
    @Override
    public int compare(Object o1, Object o2) {
        int i1 = (int)o1;
        int i2 = (int)o2;
        return i2 - i1; // 这里返回值的正负决定排序顺序
    }
});
```

这个自定义排序综合使用了匿名内部类，接口实现，动态绑定

不是返回值大小本身直接影响排序结果，而是在特定的排序规则和比较逻辑中，返回值所代表的元素之间的大小关系决定了元素在排序后的序列中的位置



System类常用方法

![image-20250708111003932](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708111003932.png)

Arrays的copy方法底层用的就是System



![image-20250708112020860](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708112020860.png)

大数据类型的运算有专门的方法，不要直接+-*/

大数据类型的精度理论上无线，实际上看机器内存空间

![image-20250708112559049](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708112559049.png)



Date

第一代日期类，搭配SimpleDateFormat，实现指定日期格式，字符串日期互转

Calendar

第二代

抽象类，构造器私有

![image-20250708120037987](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708120037987.png)

提供一堆字段，自己组合着玩去

第三代

前两代都不能处理闰年，且线程不安全

![image-20250708120305433](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708120305433.png)

DateTimeFormatter









# **JavaAPI**

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
| 6      | `<<`、`>>`、`>>>`                                            | L→R         | 算数左移、算数（带符号）右移、逻辑（无符号）右移    |                      |                  |
| 7      | `<`、`>`、`<=`、`>=`、`instanceof`                           | L→R         | 关系比较、类型判断                            |                      |                  |
| 8      | `==`、`!=`                                                   | L→R         | 相等、不相等判断                              |                      |                  |
| 9      | `&`（按位与）                                                | L→R         | 按位与运算                                    |                      |                  |
| 10     | `^`                                                          | L→R         | 按位异或                                      |                      |                  |
| 11     | `                                                            | `（按位或） | L→R                                           | 按位或运算           |                  ||
| 12     | `&&`                                                         | L→R         | 短路与（逻辑与）                              |                      |                  |
| 13     | `                                                            |             | `                                             | L→R                  | 短路或（逻辑或） |||
| 14     | `? :`                                                        | R→L         | 三元条件运算符                                |                      |                  |
| 15     | `=`、`*=`、`/=`、`%=`、`+=`、`-=`、`<<=`、`>>=`、`>>>=`、`&=`、`^=`、` | =`          | R→L                                           | 赋值及复合赋值运算符 |                  ||

三元运算符，一真大师

![image-20250707151354735](D:\01\技术\感获\md文档\JavaSE.assets\image-20250707151354735.png)

如果写true，返回选项1，false返回选项2	同时👇

![image-20250707151534294](D:\01\技术\感获\md文档\JavaSE.assets\image-20250707151534294.png)

三元运算符是一个整体，所以返回精度最高的，即Double类型1.0

也注意 ； 由；划分才是完整的一句话





关于其中<< >> >>>，参考计算机组成原理，计算机移位

| 移位类型 | 适用数据            | 符号位处理                    | 空位填补规则                                                 | 典型用途                    |
| -------- | ------------------- | ----------------------------- | ------------------------------------------------------------ | --------------------------- |
| 算术左移 | 有符号数            | 符号位不变                    | 正数补 `0`；负数依编码补（原码补 `0`，反码补 `1`，补码补 `0` ） | 实现 ×2 运算（需注意溢出 ） |
| 算术右移 | 有符号数            | 符号位不变                    | 正数补 `0`；负数依编码补（原码补 `0`，反码补 `1`，补码补 `1` ） | 实现 ÷2 运算（向下取整 ）   |
| 逻辑左移 | 无符号数            | 符号位当普通位参与移位        | 补 `0`                                                       | 快速 ×2、位模式左移调整     |
| 逻辑右移 | 无符号数            | 符号位当普通位参与移位        | 补 `0`                                                       | 快速 ÷2、位模式右移调整     |
| 循环移位 | 无符号数 / 特定场景 | 无特殊处理（或含进位标志位 ） | 溢出位补到另一端                                             | 加密、校验、多字节数据移位  |





位运算

~按位取反



**命名规则规范**

规则是必须遵守的，规范是大家共同制定的，现在也是必须遵守的

[alibaba/p3c: Alibaba Java Coding Guidelines pmd implements and IDE plugin](https://github.com/alibaba/p3c)









java**关键字保留字**

![image-20250629203846548](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629203846548.png)

![image-20250629203850812](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629203850812.png)

![image-20250629203853769](D:\01\技术\感获\md文档\JavaSE.assets\image-20250629203853769.png)





# **顺序控制**



## switch

switch(表达式)

case 常量

`switch` 表达式结果的类型，需是 **`byte`、`short`、`int`、`char`、`enum`（枚举，Java 5+）、`String`（Java 7+）、`Character`/`Byte`/`Short`/`Integer` 等包装类型（自动拆箱后符合要求）** ,final相关类型变量

不允许直接用 `long`（需显式强转成 `int` 等小范围整型）、`float`、`double` 等类型



只能是这些因为

Java 虚拟机（JVM）对 `switch` 的支持，依赖 **`tableswitch` 和 `lookupswitch` 两条核心指令**，而这两条指令**本质上只处理 `int` 类型**：

- **`tableswitch`**：适合 `case` 值连续的场景，用 `case` 值做索引直接跳转（类似数组访问，时间复杂度 `O(1)`），要求值能映射到连续 `int` 范围。
- **`lookupswitch`**：适合 `case` 值稀疏的场景，对 `int` 值逐个比较（可优化为二分查找），同样基于 `int` 处理。

其他类型能被支持，是因为 **自动类型转换或底层适配**：

- `byte`/`short`/`char`：会**隐式提升为 `int`**（如 `char` 实际按 Unicode 码值参与运算），编译后用 `int` 指令处理。
- `枚举（enum）`：编译时会取枚举的**ordinal 值（整数索引）** 参与 `switch`，本质还是 `int` 运算。
- `String`（Java 7 + 支持）：编译时通过 **`hashCode` 配合 `equals`** 转换，底层仍依赖 `int` 相关逻辑处理匹配。





## for循环

循环条件是子表达式，有boolean返回值

for(；；)  死循环	没有循环条件，但又要求循环，于是不停止循环





## break	continue	return

均可终止指定标签，不指定默认最近循环体

goto是保留字，但是为了避免与C/C++混淆，所以不能用



return 是退出方法，后有

- **`void`**：单独使用 `return;`。
- **非 `void`**：必须跟一个与返回类型兼容的值或表达式。
- **方法名返回值**：（函数式编程场景），返回形式是return 方法名（或方法引用）；但方法不能直接作为返回值，实际返回方法的执行结果

```java
import java.util.function.Supplier;

public class Main {
    public static Supplier<Integer> test() {
        return Main::getNumber; // 返回方法引用，而非方法本身
    }

    public static Integer getNumber() {
        return 42;
    }

    public static void main(String[] args) {
        Supplier<Integer> supplier = test();
        System.out.println(supplier.get()); // 输出 42
    }
}
```





# 包

## 组织类

在一个包引用另一个包中的重名类

![image-20250701122639374](D:\01\技术\感获\md文档\JavaSE.assets\image-20250701122639374.png)

## 常用包

![image-20250701122704619](D:\01\技术\感获\md文档\JavaSE.assets\image-20250701122704619.png)



![image-20250701123142993](D:\01\技术\感获\md文档\JavaSE.assets\image-20250701123142993.png)





## 访问权限

| 访问控制修饰符 | 类内部 | 同包类 | 子类（不同包） | 其他包类 |
| -------------- | ------ | ------ | -------------- | -------- |
| `public`       | √      | √      | √              | √        |
| `protected`    | √      | √      | √              | ×        |
| 默认           | √      | √      | ×              | ×        |
| `private`      | √      | ×      | ×              | ×        |

修饰符可修饰 类、字段、成员方法

类只能被publich和默认修饰



# 断点调试





![image-20250702112734794](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702112734794.png)

调用b.xx，但是因为是动态，所以看A类，所以实际是b.xx



F7	进入方法

Shift+F8	跳出方法

F8	单步执行

还有ctrl+alt+7 进入源码

👆可以学源码

F9	到下一断点

​	在一些超大业务中，可以根据断点判断有没有执行到某个业务





# main

main由jvm调用

![image-20250702162328502](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702162328502.png)



# final

![image-20250702175501520](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702175501520.png)

![image-20250702175905598](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702175905598.png)

![image-20250702180044708](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702180044708.png)

当一个变量被声明为`static final`时，它就成为了一个编译期常量。编译器在编译阶段就能确定其值，并且在编译过程中，会将所有使用该常量的地方直接替换为其实际的值。

这样就减少了运行时获取变量值的操作，节省了时间和资源 。



final修饰不同元素对它们造成不同锁定

修饰基本变量，值不可改

修饰引用类型变量时，该变量的引用地址不可改，但地址指向的对象内容是可改

修饰方法时，意味着这个方法不能被子类重写。

修饰类时，这个类不能被其他类继承









# abstract

abstract只能修饰类和方法

抽象类不是必须包含抽象方法（这时候更多是对实现类进行一定约束和规范）

但是有抽象方法的必须是抽象类

类继承了抽象类，必须实现抽象方法，除非它也声明为abstract

![image-20250702182204085](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702182204085.png)



# interface

jdk8.0后可以有静态方法，默认方法(不是普通方法，default修饰的方法)

![image-20250702184529315](D:\01\技术\感获\md文档\JavaSE.assets\image-20250702184529315.png)



接口可以很好的进行类名的规范统一(开发手册)

接口的修饰符和类一样只能是public和默认

接口不能继承类，只能继承接口

![image-20250703081128543](D:\01\技术\感获\md文档\JavaSE.assets\image-20250703081128543.png)



接口属性只能是public static final

接口属性访问形式：接口名.属性名



IDEA中只允许通过类名调用静态成员变量，但不这么做也允许通过。我想告诉自己的是：原理是可以这么做，但规范不允许这么做，遵守规范，知道原理





## 接口和继承区别

接口是对单继承的补充

![image-20250703075810659](D:\01\技术\感获\md文档\JavaSE.assets\image-20250703075810659.png)

```java
public class Main {

    public static void main(String[] args)  {

    }

    public static interface A{
        int x = 1;
    }

    public static class B{
        int x = 2;
    }

    public static class C extends B implements A{

        public void fun(){
            System.out.println(super.x+ A.x);
        }
    }

}
```







# 注解

也称 元数据

修饰	包、类、方法、属性、构造器、局部变量等

注解也参与编译运行，嵌入代码的补充说明

JavaSE中注解比较鸡肋，就是标记方法过时，忽略警告等

但它在JavaEE中很重要

<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250706151225683.png" alt="image-20250706151225683" style="zoom:50%;" />



## @Override

从编译层面检查 某方法是否重写了父类

就算不加这个注解，只要和 父类 返回值，参数列表，方法名一样，就达成重写了，加注解的目的是语法检查，检查是否重写了

## @Deprecated

jdk版本过渡



## @SuppressWarnings

抑制警告，通过输入指定字符串参数抑制指定警告

@SuppressWarnings(“all”)	//抑制所有警告

它仿制的位置就是抑制范围，如放在某变量定义语句上，范围就这一句话，如果是1个类，就抑制这个类

除了元注解，不能再注解上加注解，上面那句不是因为注解注解出错而，而是找不到要注解的东西而错

![image-20250706152550206](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706152550206.png)



## 元注解

![image-20250706154603847](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706154603847.png)





### @Rention

指定注解保留时长，只能修饰1个注解

其包含一个必须指定值的RentionPolicy类型成员变量，正是该变量控制注解保留时长

![image-20250706155037381](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706155037381.png)

3个值的区别就是注解作用时间范围

<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250706155547072.png" alt="image-20250706155547072" style="zoom: 50%;" />







### @Target

确定注解修饰的程序元素（类，构造器、局部变量、包、类型、字段、方法、参数）





### @Inherited

子类也继承注解



# 异常

出现一些不算严重的异常导致程序系统整个崩溃，这样显然不行，于是在可能出错的地方进行异常处理

异常处理实现的效果是	出了异常，程序也能继续执行



<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250706161251924.png" alt="image-20250706161251924" style="zoom:50%;" />

![image-20250706161428748](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706161428748.png)



## 运行时异常

![image-20250706161822859](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706161822859.png)

## 编译时异常

![image-20250706161938929](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706161938929.png)



## 异常处理方式

### try-catch-finally

程序员捕获异常并处理

发生异常，则跳过后续代码，直接进入catch

无论是否有异常，finally都会执行



### throws

交给调用者处理

throws可以抛出生成的异常类型，也可以是父类





默认throws，最终会给jvm，jvm处理方式就是打印异常信息，中断程序运行

处理方法2选1就行





可以会有多种异常，如果需要细分处理，就多catch



![image-20250706165743970](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706165743970.png)



<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250706171319274.png" alt="image-20250706171319274" style="zoom:50%;" />



按照 Java 语法规则，`finally` 块 **必须执行**（除非遇到 `System.exit(0)` 等强制退出 JVM 的操作） 。所以，在 `catch` 块中准备返回 `3` 时，会先进入 `finally` 块，执行 `return 4;` 。

**`return` 语句在 `try`/`catch` 块中执行时，会先 “暂存” 返回值，然后优先执行 `finally` 块，再根据 `finally` 块的情况决定最终返回结果** 





编译异常必须处理，运行异常默认throws，子类重写父类方法抛出异常和父类一致或异常子类



## 自定义异常

![image-20250706172623750](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706172623750.png)

无论怎么细分，本质还是这2类异常

```java
import java.util.Scanner;

public class Main {

    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) throws Exception {
        int age;
        age = sc.nextInt();
        if (!(age >= 18 && age <= 20)){
            throw new AgeException("年龄不对");	//调用，并传入参数
        }
    }

    static class AgeException extends RuntimeException {
        public AgeException(String message) {
            super(message);	//调用父类，参数传给父类，父类一直传到throwable，然后打印
        }
    }

}
```

![image-20250706174948889](D:\01\技术\感获\md文档\JavaSE.assets\image-20250706174948889.png)



```java
import java.io.IOException;
import java.util.Scanner;

public class Main {

    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) throws Exception {

        try{
            say();
        }catch (RuntimeException e){
            System.out.println(e.getMessage());
        }
    }

    static void say(){

        throw new RuntimeException("dasd");
    }

}
```



# 集合

数组的不足就是存储同类，增删困难，长度固定

集合可动态存储任意多对象并有配套操作方法

注意	是否允许重复、是否有序、是否支持索引

![image-20250708122947369](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708122947369.png)

![image-20250708123331388](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708123331388.png)![image-20250708123340105](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708123340105.png)



## Collection

没有直接实现类，靠子接口Set、List实现

## 迭代器

![image-20250708131704004](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708131704004.png)

![image-20250708132105966](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708132105966.png)

还有foreach





## List

元素有序可重复，支持索引

### ArrayList

线程不安全，基本等同Vector，可存储null（允许多个）

![image-20250708135428333](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708135428333.png)

java的扩容机制就是 创建新数组，复制原数组内容至新数组

`ArrayList`的扩容公式为：

初始为10

其后

**新容量 = 旧容量 + (旧容量>> 1)**
其中，`旧容量 >> 1` 表示将旧容量右移一位（相当于除以 2 并向下取整）

若新容量（4）仍小于 **最小所需容量**（例如添加第 4 个元素时，最小所需容量为 4），则直接使用 **最小所需容量**。
因此，最终容量为 **4**。	

transient表示属性不会被序列化



### Vector

无参，默认10，之后2倍



### LinkedList

底层维护双向链表

![image-20250708143247412](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708143247412.png)



## Set

无序、不允许重复、不支持索引

最多1个null



使用add（）会返回布尔值，若重复添加返回false，重复元素不会被加入set

![image-20250708145206910](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708145206910.png)

这种情况不算重复元素，都能加进去

![image-20250708145320471](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708145320471.png)



set确定元素是否重复的机制是：





### HashSet

底层是	数组+链表+红黑树



![image-20250708150108497](D:\01\技术\感获\md文档\JavaSE.assets\image-20250708150108497.png)



### LinkedHashSet

<img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250708162942195.png" alt="image-20250708162942195" style="zoom:50%;" />

 <img src="D:\01\技术\感获\md文档\JavaSE.assets\image-20250709084313969.png" alt="image-20250709084313969" style="zoom:50%;" />

 ![image-20250709084245594](D:\01\技术\感获\md文档\JavaSE.assets\image-20250709084245594.png)

`nkedHashMap` 是 `HashMap` 的子类，`LinkedHashMap` 内部的 `Entry` 其实是继承自 `HashMap.Node` 并做了扩展



## Map

![image-20250709090612679](D:\01\技术\感获\md文档\JavaSE.assets\image-20250709090612679.png)

key相同，map便视作相同元素

对于元素相同的情况，map不像set那样不加入，而是替换掉

![image-20250709092255627](D:\01\技术\感获\md文档\JavaSE.assets\image-20250709092255627.png)

Node实现了Map.Entry接口，进行了向上转型

![image-20250709092637749](D:\01\技术\感获\md文档\JavaSE.assets\image-20250709092637749.png)

  包装好几层也是为了方便使用，套娃一样，Node包装key，value。entry包装node，enrtySet包装entry



Map迭代方式，有3种，每种都能用迭代器，共6种

```java
import java.io.IOException;
import java.util.*;

public class Main {

    static Scanner sc = new Scanner(System.in);

    public static void main(String[] args) throws Exception {

        Map map = new HashMap();
        map.put("1", "1");
        map.put("2", "2");
        map.put("3", "3");
        map.put("4", "4");
        map.put("5", "5");

        Set keySet = map.keySet();

        // 1 通过keySet集合
        for (Object key : keySet) {
            System.out.println(map.get(key));
        }

        Iterator it = keySet.iterator();
        while (it.hasNext()) {
            System.out.println(map.get(it.next()));
        }

        // 2 通过values
        Collection values = map.values();
        for (Object value : values){
            System.out.println(value);
        }

        // 3 通过EntrySet
        Set entrySet = map.entrySet();
        for (Object entry : entrySet){
            Map.Entry m = (Map.Entry) entry;
            System.out.println(m.getKey());
        }

        Iterator iterator = entrySet.iterator();
        while (iterator.hasNext()){
            Map.Entry m = (Map.Entry) iterator.next();
            System.out.println(m.getValue());
        }

    }

    public static class Node{
        int age;
    }

    public static class Nodee extends Node{

    }
}

```































































































































































































