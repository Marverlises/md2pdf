# MD2PDF

[English Documentation](./README.en.md) | [中文文档](./README.md)

A powerful Markdown to PDF conversion tool based on Pandoc and XeLaTeX, supporting Chinese text, mathematical formulas, code highlighting, and images.

## Features

- ✅ Convert Markdown files to high-quality PDFs
- ✅ Full support for Chinese fonts
- ✅ Support for mathematical formulas (LaTeX syntax)
- ✅ Code block syntax highlighting
- ✅ Support for images (local paths or remote URLs)
- ✅ Automatic table of contents generation (optional)
- ✅ Customizable output paths
- ✅ Cross-platform support (Windows, MacOS, Linux) — currently only tested on Ubuntu 20.04

## Installation Requirements

### 1. Install Python 3.6+

Download and install from the [Python website](https://www.python.org/downloads/).

### 2. Install Pandoc

Download and install the latest version from the [Pandoc website](https://pandoc.org/installing.html).

### 3. Install a LaTeX Distribution

Choose a LaTeX distribution suitable for your operating system:

- **Windows**: [MiKTeX](https://miktex.org/download) or [TeX Live](https://tug.org/texlive/acquire-netinstall.html)
- **MacOS**: [MacTeX](https://tug.org/mactex/mactex-download.html)
- **Linux**: TeX Live (`sudo apt install texlive-xetex texlive-fonts-recommended texlive-latex-recommended` on Ubuntu/Debian)

Make sure the installation includes XeLaTeX and Chinese font support.

## Usage

### Basic Usage

```bash
python md2pdf.py your_markdown_file.md
```

This will generate `your_markdown_file.pdf` in the same directory.

### Advanced Usage

```bash
python md2pdf.py your_markdown_file.md -o output.pdf --mainfont "SimSun" --engine xelatex --toc --verbose
```

### Command Line Arguments

| Parameter | Description |
|------|------|
| `input` | Input Markdown file path |
| `-o, --output` | Output PDF file path (default: input filename + .pdf) |
| `--mainfont` | Specify main font (default: automatically selected based on system) |
| `--engine` | PDF engine, options: xelatex/pdflatex/lualatex (default: xelatex) |
| `--toc` | Generate table of contents |
| `-v, --verbose` | Display detailed logs |
| `--debug` | Enable debug mode, showing more detailed information |

## Markdown Writing Tips

For best results, follow these writing guidelines:

### Images

```markdown
![Image description](./path/to/image.png)
```

Ensure image paths are correct, relative paths are recommended.

### Mathematical Formulas

Inline formula:

```markdown
$E=mc^2$
```

Display formula:

```markdown
$$
\frac{d}{dx}e^x = e^x
$$
```

### Code Blocks

```markdown
```python
def hello():
    print("Hello World")
```
```

## Common Issues

### Q: PDF generated successfully but cannot be opened automatically?

A: This typically happens in environments without a graphical interface (such as servers or containers). The PDF file has been successfully generated, but the system doesn't have a PDF viewer installed or cannot launch graphical applications. Please manually copy the generated PDF file to an environment with a PDF viewer.

This issue may occur in the following situations:
- Running the script on a remote server
- Running the script in a container (such as Docker)
- No PDF viewer installed on the system
- Running the script in an environment without a graphical interface

### Q: Chinese characters appear as boxes or garbled text in the generated PDF?

A: Make sure you specify the correct Chinese font, for example:
```bash
python md2pdf.py input.md --mainfont "SimSun"
```

Common Chinese fonts for different systems:
- Windows: SimSun, Microsoft YaHei
- MacOS: STSong, STHeiti, PingFang SC
- Linux: Noto Sans CJK SC, AR PL KaitiM GB

### Q: Images don't display?

A: Make sure image paths are correct, relative paths are recommended. If the path contains spaces or special characters, use quotes.

### Q: How to generate a more attractive PDF?

A: You can adjust the font and add a table of contents, for example:
```bash
python md2pdf.py input.md --mainfont "Microsoft YaHei" --toc
```

## Contribution

Issues and Pull Requests are welcome!

## Examples
**Original Content**
- [example.md](./example.md)

**Exported Content**
- [example.pdf](./example.pdf) 