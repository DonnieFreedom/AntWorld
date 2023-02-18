# C# for循环

[Microsoft C# 编码约定](https://learn.microsoft.com/zh-cn/dotnet/csharp/fundamentals/coding-style/coding-conventions)

[Microsoft C# 参考](https://learn.microsoft.com/zh-cn/previous-versions/visualstudio/visual-studio-2012/618ayhy6(v=vs.110))

[Microsoft C#文档](https://learn.microsoft.com/zh-cn/dotnet/csharp/)



- ### for 循环语法格式

- ### 嵌套循环

- ### 死循环

>

for循环语法格式如下所示：

```
for(初始化语句; 判断条件; 迭代器){ 
    // 循环主体（要执行的代码）
} 
```

for 循环语句的执行流程如下: 

- 首先执行初始化语句（通常是一个变量），并且只执行一次，在某些情况下初始化语句可以省略，只保留后面的分号即可；

- 进行条件判断，如果为 true，则执行循环主体，如果为假，则跳出 for 循环，执行 for 循环以外的代码；

- 循环主体执行完成后，更新迭代器的值（增加或减少），然后再进行条件判断，如果为真则再次执行循环主体，重复执行此步骤，直至判断条件为假，跳出循环。

### 嵌套循环

```
for(int i = 1; i <= 9; i++){
	for(int j = 1; j <= i; j++){
		Console.Write("{0} x {1} = {2}  ", j, i, i*j);
	}
	Console.WriteLine();
}
```

### 无限循环

```
for (; ;) 
{ 
Console.WriteLine("loading！"); 
}   
```

