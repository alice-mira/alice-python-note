[Python 内建函数列表](https://xplanc.org/primers/document/zh/02.Python/99.API%20%E5%B8%AE%E5%8A%A9%E6%89%8B%E5%86%8C/00.%E5%86%85%E5%BB%BA%E5%87%BD%E6%95%B0.md) > [Python 的内置函数 compile](https://xplanc.org/primers/document/zh/02.Python/EX.%E5%86%85%E5%BB%BA%E5%87%BD%E6%95%B0/EX.compile.md)

Python 的内置函数 `compile()` 是一个强大的工具，它允许将源代码编译为代码对象或 AST（抽象语法树）对象。该函数主要用于动态执行 Python 代码，常见于需要运行时编译代码的场景。

### 基本语法
```python
compile(source, filename, mode, flags=0, dont_inherit=False, optimize=-1)
    '''
    将字符串或文件编译成代码或 AST 对象

    :param source: 字符串、字节字符串，或者 AST 对象
    :param filename: 文件名或 '<string>'
    :param mode: 'exec', 'eval' 或 'single'
    :param flags: 特性
    :param dont_inherit: 是否继承
    :param optimize: 优化级别
    :return: 代码或 AST 对象
    '''
```

## 使用示例
1. 编译表达式：
```python
code = compile('3 + 5 * 2', '<string>', 'eval')
result = eval(code)  # 结果为13
```

[点击运行](https://xplanc.org/shift/?lang=python&code=Y29kZSUyMCUzRCUyMGNvbXBpbGUoJzMlMjAlMkIlMjA1JTIwKiUyMDInJTJDJTIwJyUzQ3N0cmluZyUzRSclMkMlMjAnZXZhbCcpJTBBcmVzdWx0JTIwJTNEJTIwZXZhbChjb2RlKSUyMCUyMCUyMyUyMCVFNyVCQiU5MyVFNiU5RSU5QyVFNCVCOCVCQTEzJTBBcHJpbnQocmVzdWx0KQ%3D%3D)

2. 编译多行代码：
```python
code = """\
def greet(name):
    return f"Hello, {name}!"
"""
compiled = compile(code, 'greet_module', 'exec')
exec(compiled)
print(greet("Alice"))  # 输出：Hello, Alice!
```

[点击运行](https://xplanc.org/shift/?lang=python&code=Y29kZSUyMCUzRCUyMCUyMiUyMiUyMiU1QyUwQWRlZiUyMGdyZWV0KG5hbWUpJTNBJTBBJTIwJTIwJTIwJTIwcmV0dXJuJTIwZiUyMkhlbGxvJTJDJTIwJTdCbmFtZSU3RCElMjIlMEElMjIlMjIlMjIlMEFjb21waWxlZCUyMCUzRCUyMGNvbXBpbGUoY29kZSUyQyUyMCdncmVldF9tb2R1bGUnJTJDJTIwJ2V4ZWMnKSUwQWV4ZWMoY29tcGlsZWQpJTBBcHJpbnQoZ3JlZXQoJTIyQWxpY2UlMjIpKSUyMCUyMCUyMyUyMCVFOCVCRSU5MyVFNSU4NyVCQSVFRiVCQyU5QUhlbGxvJTJDJTIwQWxpY2Uh)

Python 的内置函数 `compile()` 是用于将 Python 源代码编译为可执行代码对象的重要工具。这个函数接收源代码字符串作为输入，并将其转换为可以被 `exec()` 或 `eval()` 执行的代码对象。

### 函数签名
```python
compile(source, filename, mode, flags=0, dont_inherit=False, optimize=-1)
```

### 参数详解
1. **source**：
   - 必须参数，表示要编译的 Python 源代码
   - 可以是字符串、字节字符串或 AST（抽象语法树）对象
   - 示例：
     ```python
     source_code = "print('Hello, World!')"
     ```

2. **filename**：
   - 指定源代码的文件名
   - 如果代码不是从文件中读取的，可以传递任意可识别的名称（如 "<string>"）
   - 该名称会出现在错误信息中
   - 示例：
     ```python
     filename = "example.py"
     ```

3. **mode**：
   - 指定编译模式，有三种可选值：
     - `'exec'`：用于编译模块级代码（可以包含多条语句）
     - `'eval'`：用于编译单个表达式
     - `'single'`：用于编译交互式语句（如 REPL 环境中的单条语句）
   - 示例：
     ```python
     mode = 'exec'
     ```

4. **flags**（可选）：
   - 控制编译器的行为
   - 可以是 `__future__` 特征的组合（如 `compiler.PyCF_ALLOW_TOP_LEVEL_AWAIT`）

5. **dont_inherit**（可选）：
   - 布尔值，默认为 False
   - 如果为 True，则编译时不会继承当前环境的 `__future__` 特征

6. **optimize**（可选）：
   - 指定优化级别：
     - `-1`：使用解释器的 `-O` 选项值
     - `0`：不优化
     - `1` 或 `2`：不同程度的优化

### 返回值
函数返回一个代码对象，该对象可以传递给 `exec()` 或 `eval()` 执行。

### 使用示例
1. [基本用法](https://xplanc.org/shift/index.html?lang=python&code=Y29kZSUyMCUzRCUyMGNvbXBpbGUoJ3ByaW50KCUyMkhlbGxvJTIyKSclMkMlMjAnJTNDc3RyaW5nJTNFJyUyQyUyMCdleGVjJyklMEFleGVjKGNvZGUp)：
```python
code = compile('print("Hello")', '<string>', 'exec')
exec(code)
```

2. [表达式评估](https://xplanc.org/shift/index.html?lang=python&code=ZXhwcmVzc2lvbiUyMCUzRCUyMGNvbXBpbGUoJzMlMjAlMkIlMjA1JTIwKiUyMDInJTJDJTIwJyUzQ3N0cmluZyUzRSclMkMlMjAnZXZhbCcpJTBBcmVzdWx0JTIwJTNEJTIwZXZhbChleHByZXNzaW9uKSUyMCUyMCUyMyUyMCVFOCVCRiU5NCVFNSU5QiU5RSUyMDEzJTBBcHJpbnQocmVzdWx0KQ%3D%3D)：
```python
expression = compile('3 + 5 * 2', '<string>', 'eval')
result = eval(expression)  # 返回 13
```

3. [交互式模式](https://xplanc.org/shift/index.html?lang=python&code=Y29kZSUyMCUzRCUyMGNvbXBpbGUoJ3glMjAlM0QlMjA1JTNCeSUyMCUzRCUyMDEwJTNCeCUyMCUyQiUyMHknJTJDJTIwJyUzQ3N0cmluZyUzRSclMkMlMjAnc2luZ2xlJyklMEFleGVjKGNvZGUpJTIwJTIwJTIzJTIwJUU0JUJDJTlBJUU4JUJFJTkzJUU1JTg3JUJBJTIwMTU%3D)：
```python
code = compile('x = 5\ny = 10\nx + y', '<string>', 'single')
exec(code)  # 会输出 15
```

### 应用场景
1. 动态代码执行：当需要从配置文件或用户输入中获取并执行代码时
2. 代码优化：在需要多次执行相同代码时，先编译可提高性能
3. 元编程：构建代码生成工具或DSL（领域特定语言）时

### 注意事项
1. 使用 `compile()` 执行不可信代码存在安全风险
2. 编译后的代码对象不能跨 Python 版本使用
3. 在大多数情况下，直接使用 `eval()` 或 `exec()` 更方便

### 错误处理
```python
try:
    code = compile(invalid_code, '<string>', 'exec')
except SyntaxError as e:
    print(f"Syntax error: {e}")
```

通过合理使用 `compile()` 函数，可以实现更灵活和高效的 Python 代码执行方式。
