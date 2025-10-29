[Python 内建函数列表](https://xplanc.org/primers/document/zh/02.Python/99.API%20%E5%B8%AE%E5%8A%A9%E6%89%8B%E5%86%8C/00.%E5%86%85%E5%BB%BA%E5%87%BD%E6%95%B0.md) > [Python 的内置函数 eval](https://xplanc.org/primers/document/zh/02.Python/EX.%E5%86%85%E5%BB%BA%E5%87%BD%E6%95%B0/EX.eval.md)

Python 的内置函数 `eval()` 是一个强大的功能函数，用于执行动态生成的 Python 表达式。它的完整语法是：

```python
eval(expression, globals=None, locals=None)
```

其中：
- `expression` 是必需参数，表示要执行的字符串形式的 Python 表达式
- `globals` 是可选的全局变量字典
- `locals` 是可选的局部变量字典

[示例](https://xplanc.org/shift/?lang=python&code=eCUyMCUzRCUyMDEwJTBBcmVzdWx0JTIwJTNEJTIwZXZhbCglMjJ4JTIwJTJCJTIwNSUyMiklMjAlMjAlMjMlMjAlRTglQkYlOTQlRTUlOUIlOUUlMjAxNSUwQXByaW50KHJlc3VsdCk%3D)：
```python
x = 10
result = eval("x + 5")  # 返回 15
print(result)
```

安全注意事项：
1. `eval()` 可以执行任意代码，存在严重的安全风险
2. 永远不要直接执行来自不可信来源的输入

典型应用场景：
1. 数学表达式计算器
2. 配置参数解析
3. 简单脚本执行


