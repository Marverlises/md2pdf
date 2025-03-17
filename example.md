# MD2PDF 示例文档

这是一个示例文档，用于展示 md2pdf 工具支持的各种 Markdown 功能。

## 1. 基本文本格式

你可以使用 **粗体**、*斜体* 或 ***粗斜体***。

也可以使用 ~~删除线~~ 效果。

## 2. 列表

### 无序列表

- 项目一
- 项目二
  - 子项目 2.1
  - 子项目 2.2
- 项目三

### 有序列表

1. 第一步
2. 第二步
   1. 子步骤 2.1
   2. 子步骤 2.2
3. 第三步

## 3. 引用

> 这是一段引用文本。
> 
> 引用可以有多个段落。
>> 也可以嵌套引用。

## 4. 代码

行内代码：`print("Hello, World!")`

代码块：

```python
def factorial(n):
    if n == 0 or n == 1:
        return 1
    else:
        return n * factorial(n-1)

# 计算 5 的阶乘
result = factorial(5)
print(f"5! = {result}")
```

## 5. 表格

| 名称 | 类型 | 描述 |
|------|------|------|
| id | int | 用户ID |
| name | string | 用户名 |
| email | string | 电子邮件 |
| active | boolean | 是否激活 |

## 6. 链接和图片

### 链接

[Markdown 指南](https://www.markdownguide.org)

### 图片

![示例图片](https://via.placeholder.com/300x200)

## 7. 数学公式

行内公式：$E = mc^2$

独立公式：

$$
\frac{d}{dx}\left( \int_{a}^{x} f(t) \, dt \right) = f(x)
$$

矩阵：

$$
A = \begin{pmatrix}
a_{11} & a_{12} & a_{13} \\
a_{21} & a_{22} & a_{23} \\
a_{31} & a_{32} & a_{33}
\end{pmatrix}
$$

## 8. 脚注

这是一个带有脚注的文本[^1]。

[^1]: 这是脚注内容。

## 9. 任务列表

- [x] 已完成任务
- [ ] 未完成任务
- [ ] 待办事项

## 10. 水平线

---

## 11. 定义列表

术语 1
: 定义 1

术语 2
: 定义 2a
: 定义 2b

## 12. LaTeX 特殊符号

符号示例：$\alpha, \beta, \gamma, \delta, \epsilon, \zeta, \eta, \theta$

集合：$\{1, 2, 3\} \subset \mathbb{N}$

## 13. 中文排版示例

### 中文标题与正文

这是一段中文示例文本，用于测试中文字体渲染效果。

春眠不觉晓，
处处闻啼鸟。
夜来风雨声，
花落知多少。

### 中英混排

这是一段中英混排的文本，English text mixed with Chinese characters。

---

*文档结束* 