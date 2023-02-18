# C# break、continue、goto：跳出循环

[Microsoft C# 编码约定](https://learn.microsoft.com/zh-cn/dotnet/csharp/fundamentals/coding-style/coding-conventions)

[Microsoft C# 参考](https://learn.microsoft.com/zh-cn/previous-versions/visualstudio/visual-studio-2012/618ayhy6(v=vs.110))

[Microsoft C#文档](https://learn.microsoft.com/zh-cn/dotnet/csharp/)

### break

- 在循环语句中, 跳出循环，执行循环外的下一条语句。

### continue

- 在循环语句中, 跳过本次循环继续执行下一次的循环。

### goto 

- goto 语句也称为跳转语句, 使用它可以控制程序跳转到指定的位置执行。而且多次使用会使程序变得更加复杂
- goto 语句并不限于在循环中使用，其它的情况也可以使用。但是，goto 语句不能从循环外跳转到循环语句中，而且不能跳出类的范围。
- goto语句格式如下:

```
goto Labels;

语句块1;
Labels:
    语句块2;
```

```C#
using System;
namespace c.biancheng.net
{
    class Demo
    {
        static void Main(string[] args){
            int count = 1;
            login:
                Console.WriteLine("请输入用户名");
                string username = Console.ReadLine();
                Console.WriteLine("请输入密码");
                string userpwd = Console.ReadLine();
            if (username == "c.biancheng.net" && userpwd == "123456"){
                Console.WriteLine("登录成功");
            }else{
                count++;
                if (count > 3){
                    Console.WriteLine("用户名或密码错误次数过多！退出！");
                }else{
                    Console.WriteLine("用户名或密码错误");
                    goto login;//返回login标签处重新输入用户名密码
                }
            }
        }
    }
}
```

```C#
using System;
namespace c.biancheng.net
{
    class Demo
    {
        static void Main(string[] args){
            Console.WriteLine("请输入学生考试的成绩（0~100的整数）");

			int points = 77;
            switch (points / 10)
            {
                case 10:
                    Console.WriteLine("优秀");
                    break;
                case 9:
                    Console.WriteLine("优秀");
                    break;
                case 8:
                    Console.WriteLine("良好");
                    break;
                case 7:
                    Console.WriteLine("及格");
                    goto case 10;
                case 6:
                    Console.WriteLine("及格");
                    break;
                default:
                    Console.WriteLine("不及格");
                    break;
            }
        }
    }
}
```

