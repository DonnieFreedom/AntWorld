# C# this关键字

[Microsoft C# 编码约定](https://learn.microsoft.com/zh-cn/dotnet/csharp/fundamentals/coding-style/coding-conventions)

[Microsoft C# 参考](https://learn.microsoft.com/zh-cn/previous-versions/visualstudio/visual-studio-2012/618ayhy6(v=vs.110))

[Microsoft C#文档](https://learn.microsoft.com/zh-cn/dotnet/csharp/)

在 C# 中，可以使用 this 关键字来表示当前对象，来访问类中的成员属性以及函数以及一些其它用法



- #### 使用 this 表示当前类的对象

- #### 使用 this 关键字串联构造函数

- #### 使用 this 关键字作为类的索引器

- #### 使用 this 关键字作为原始类型的扩展方法

> 

```C#
using System;
namespace c.sharp
{
    class Demo
    {
        static void Main(string[] args) 
        {
            // 使用 this 表示当前类的对象
            T1 t1 = new T1("C#","unity");
            t1.Display();
            // 使用 this 关键字串联构造函数
            T2 t2 = new T2("C#");
            // 使用 this 关键字作为类的索引器
            T3 a = new T3();
            Console.WriteLine("Temp0:{0}, Temp1:{1}", a[0], a[1]);
            a[0] = 15;
            a[1] = 20;
            a[2] = 25;
            Console.WriteLine("Temp0:{0}, Temp1:{1}", a[0], a[2]);
            // 使用 this 关键字作为原始类型的扩展方法
            string str = "C#";
            string newstr = str.ExpandString();
            Console.WriteLine(newstr);
        }
    }
    public class T1
    {
        private string name;
        private string url;
        public T1(string n, string u){
            this.name = n;
            this.url = u;
        }
        public void Display(){
            Console.WriteLine(name +" "+ url);
        }
    }
    
    public class T2
    {
        public T2()
        {
            Console.WriteLine("无参构造函数");
        }
        // 这里的 this()代表无参构造函数 T2()
　　     // 先执行 T2()，后执行 T2(string text)
        public T2(string text) : this()
        {
            Console.WriteLine(text);
            Console.WriteLine("实例构造函数");
        }
    }
    
    public class T3
    {
        int Temp0;
        int Temp1;
        public int this[int index]
        {
            get
            {
                return (0 == index) ? Temp0 : Temp1;
            }
    
            set
            {
                if (0==index)
                    Temp0 = value;
                else
                    Temp1 = value;
            }
        }
    }
    public static class T4
    {
        public static string ExpandString(this string name)
        {
            return name+" http://c.sharp.com/";
        }
    }
}
```

```C#
// 输出
/*
C# http://c.sharp.com/

无参构造函数
C#
实例构造函数

Temp0:0, Temp1:0
Temp0:15, Temp1:25

C# http://c.sharp.com/
*/
```

