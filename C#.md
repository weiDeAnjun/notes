# C++++



C# 拥有许多现代的语言特性，如属性（Properties）、事件（Events）、委托（Delegates）、LINQ（Language Integrated Query）等，这些特性在 C 和 C++ 中是没有的。





C# 的属性可以方便地封装类的字段：

```csharp
class Person {
    private string name;

    public string Name {
        get { return name; }
        set { name = value; }
    }
}

// name是字段、Name是属性

字段是类或结构体中用于存储数据的变量
属性是一种特殊的类成员，由 get 和 set 访问器组成,它提供了对类中字段的访问和修改方式，本质上是一对 get 和 set 方法。通过属性，可以对字段的访问和修改进行控制，同时提供了更简洁和安全的语法。
	//	2025年3月16日
    我之前一直把字段当属性,,ԾㅂԾ,,
```





C# 某些基本语法上与 C 和 C++ 相似，但在内存管理、面向对象特性、命名空间、类型安全和语言特性等方面存在很大差异，因此不能说 C# 完全兼容 C++ 或 C 的语法。

```c#
class Person {
    private string name;

    public string Name {
        get { return name; }
        set { name = value; }
    }
}
```





```c#
using System;

namespace Project1
{
    class Program
    {
        static void Main(string[] args)
        {
			Console.Write("");
        	float x = float.Parse(Console.ReadLine());
        	int sng;
        }
    }
}

Console.Write("sng({0})={1} ", x, sng);
Console.Write($"sng({x})={sng}");


```











## C#类



| 访问修饰符           | 访问范围                                                   |
| -------------------- | ---------------------------------------------------------- |
| `public`             | 可以被任何程序集中的代码访问，没有访问限制。               |
| `private`            | 只能在声明它的类或结构体内部访问，是访问范围最小的修饰符。 |
| `protected`          | 可以在声明它的类及其派生类中访问。                         |
| `internal`           | 只能在同一程序集内访问。                                   |
| `protected internal` | 可以在同一程序集内访问，或者在不同程序集的派生类中访问。   |
| `private protected`  | 只能在声明它的类及其同一程序集内的派生类中访问。           |



`virtual`

修饰符，被virtual修饰的成员可在派生类重写



`=>`

`=>` 是 C# 中的表达式体成员语法，它提供了一种简洁的方式来定义方法、属性、构造函数、终结器或索引器等成员。当成员的逻辑比较简单，只包含一个表达式时，可以使用 `=>` 来简化代码。

就是简化成员定义

```c#
using System;

class Rectangle
{
    private double length;
    private double width;

    public Rectangle(double length, double width)
    {
        this.length = length;
        this.width = width;
    }

    // 使用 => 定义属性的 get 访问器
    public double Area => length * width;

    // 使用 => 定义方法
    public void PrintArea() => Console.WriteLine($"矩形的面积是: {Area}");
}

class Program
{
    static void Main()
    {
        Rectangle rect = new Rectangle(5, 3);
        rect.PrintArea(); // 输出: 矩形的面积是: 15
    }
}
```





class internal Son : Father

派生











































