# C# while循环

[Microsoft C# 编码约定](https://learn.microsoft.com/zh-cn/dotnet/csharp/fundamentals/coding-style/coding-conventions)

[Microsoft C# 参考](https://learn.microsoft.com/zh-cn/previous-versions/visualstudio/visual-studio-2012/618ayhy6(v=vs.110))

[Microsoft C#文档](https://learn.microsoft.com/zh-cn/dotnet/csharp/)



- ### while循环语法格式

- ### 嵌套循环

语法格式如下所示：

```
while(表达式){
    循环主体;         // 要执行的代码
}
```

执行过程如下

- 判断表达式, 如果为真则执行循环主体, 为假, 跳出循环

### 嵌套循环

```
int i = 1;
while(i <= 9){
	int j = 1;
	while(j <= i){
		Console.Write("{0} x {1} = {2}  ", j, i, i*j);
		j++;
	}
	i++;
	Console.WriteLine();
}
```

