# MD2PDF

[English Documentation](./README.en.md) | 中文文档

一个功能强大的 Markdown 转 PDF 工具，基于 Pandoc 和 XeLaTeX，支持中文、数学公式、代码高亮和图片。

## 功能特点

- ✅ 将 Markdown 文件转换为高质量 PDF
- ✅ 完整支持中文字体
- ✅ 支持数学公式（LaTeX 语法）
- ✅ 代码块语法高亮
- ✅ 支持图片（本地路径或远程URL）
- ✅ 自动生成目录（可选）
- ✅ 自定义输出路径
- ✅ 跨平台支持（Windows、MacOS、Linux）—— 但目前仅在 Ubuntu 20.04 上测试过

## 安装依赖

### 1. 安装 Python 3.6+

从 [Python 官网](https://www.python.org/downloads/) 下载并安装。

### 2. 安装 Pandoc

从 [Pandoc 官网](https://pandoc.org/installing.html) 下载并安装最新版本。

### 3. 安装 LaTeX 发行版

选择适合您操作系统的 LaTeX 发行版：

- **Windows**: [MiKTeX](https://miktex.org/download) 或 [TeX Live](https://tug.org/texlive/acquire-netinstall.html)
- **MacOS**: [MacTeX](https://tug.org/mactex/mactex-download.html)
- **Linux**: TeX Live (`sudo apt install texlive-xetex texlive-fonts-recommended texlive-latex-recommended` 在 Ubuntu/Debian)

确保安装包含 XeLaTeX 和中文字体支持。

## 使用方法

### 基本用法

```bash
python md2pdf.py your_markdown_file.md
```

这将在同一目录下生成 `your_markdown_file.pdf`。

### 高级用法

```bash
python md2pdf.py your_markdown_file.md -o output.pdf --mainfont "SimSun" --engine xelatex --toc --verbose
```

### 命令行参数

| 参数 | 说明 |
|------|------|
| `input` | 输入的 Markdown 文件路径 |
| `-o, --output` | 输出的 PDF 文件路径（默认：输入文件名+.pdf） |
| `--mainfont` | 指定主字体（默认：根据系统自动选择） |
| `--engine` | PDF 引擎，可选 xelatex/pdflatex/lualatex（默认：xelatex） |
| `--toc` | 生成目录 |
| `-v, --verbose` | 显示详细日志 |
| `--debug` | 启用调试模式，显示更多详细信息 |

## Markdown 写作建议

为获得最佳效果，建议遵循以下写作规范：

### 图片

```markdown
![图片说明](./path/to/image.png)
```

确保图片路径正确，推荐使用相对路径。

### 数学公式

行内公式：

```markdown
$E=mc^2$
```

独立公式：

```markdown
$$
\frac{d}{dx}e^x = e^x
$$
```

### 代码块

```markdown
​```python
def hello():
    print("Hello World")
​```
```

## 常见问题

### Q: PDF生成成功但无法自动打开？

A: 这通常发生在没有图形界面的环境（如服务器或容器）中。PDF文件已成功生成，但系统没有安装PDF查看器或无法启动图形应用程序。请手动将生成的PDF文件复制到有PDF查看器的环境中查看。

在以下情况下可能会出现此问题：
- 在远程服务器上运行脚本
- 在容器（如Docker）中运行脚本
- 系统中没有安装PDF查看器
- 在无图形界面的环境中运行脚本

### Q: 生成的 PDF 中文显示为方块或乱码？

A: 确保指定了正确的中文字体，例如：
```bash
python md2pdf.py input.md --mainfont "SimSun"
```

不同系统的常用中文字体：
- Windows: SimSun, Microsoft YaHei
- MacOS: STSong, STHeiti, PingFang SC
- Linux: Noto Sans CJK SC, AR PL KaitiM GB

### Q: 图片无法显示？

A: 确保图片路径正确，建议使用相对路径。如果路径包含空格或特殊字符，请使用引号括起来。

### Q: 如何生成更漂亮的 PDF？

A: 可以调整字体、添加目录，例如：
```bash
python md2pdf.py input.md --mainfont "Microsoft YaHei" --toc
```

## 贡献

欢迎提交 Issues 和 Pull Requests！ 

## 示例
**原始内容**
- [example.md](./example.md)

**导出内容**
- [example.pdf](./example.pdf)