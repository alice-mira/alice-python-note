[Python 内建函数列表](https://xplanc.org/primers/document/zh/02.Python/99.API%20%E5%B8%AE%E5%8A%A9%E6%89%8B%E5%86%8C/00.%E5%86%85%E5%BB%BA%E5%87%BD%E6%95%B0.md) > [Python 的内置函数 callable](https://xplanc.org/primers/document/zh/02.Python/EX.%E5%86%85%E5%BB%BA%E5%87%BD%E6%95%B0/EX.bytearray.md)

Python 的内置函数 `chr()` 是一个非常有用的函数，它用于将 Unicode 编码的整数转换为对应的字符。该函数的语法非常简单：

```python
chr(i)
```

### 使用示例
[运行](https://xplanc.org/shift/?lang=python&code=JTIzJTIwJUU1JTlGJUJBJUU2JTlDJUFDJTIwQVNDSUklMjAlRTUlQUQlOTclRTclQUMlQTYlMEFwcmludChjaHIoNjUpKSUyMCUyMCUyMyUyMCVFOCVCRSU5MyVFNSU4NyVCQSUzQSUyMCdBJyUwQXByaW50KGNocig5NykpJTIwJTIwJTIzJTIwJUU4JUJFJTkzJUU1JTg3JUJBJTNBJTIwJ2EnJTBBJTBBJTIzJTIwJUU0JUI4JUFEJUU2JTk2JTg3JUU2JUIxJTg5JUU1JUFEJTk3JTBBcHJpbnQoY2hyKDIwMDEzKSklMjAlMjAlMjMlMjAlRTglQkUlOTMlRTUlODclQkElM0ElMjAnJUU0JUI4JUFEJyUwQXByaW50KGNocigyMjI2OSkpJTIwJTIwJTIzJTIwJUU4JUJFJTkzJUU1JTg3JUJBJTNBJTIwJyVFNSU5QiVCRCc%3D)
```python
# 基本 ASCII 字符
print(chr(65))  # 输出: 'A'
print(chr(97))  # 输出: 'a'

# 中文汉字
print(chr(20013))  # 输出: '中'
print(chr(22269))  # 输出: '国'
```

**注意事项**：
   - 确保输入的整数在有效范围内
   - 不同 Python 版本对 Unicode 的支持可能略有差异
   - 某些编码可能无法在某些终端/环境中正确显示

这个函数在处理文本编码、字符转换等任务时非常实用，特别是在需要生成或解码特定字符的场合。
