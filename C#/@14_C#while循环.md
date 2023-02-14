# C# while循环

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

