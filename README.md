<h1 align="center">Textura</h1>

<p align="center">
 **Textura** is a Python package for terminal text styling, similar to **colorama**, but with more features and flexibility. With Textura, you can easily add foreground colors, background colors, and text styles (bold, italic, underline) to your terminal output.
</p>

<p align="center">
  <a href="https://pypi.org/project/textura/"><img src="https://badge.fury.io/py/textura.svg" alt="PyPI version"></a>
  <a href="https://github.com/imAnesYT/easydb/blob/main/LICENSE"><img src="https://img.shields.io/github/license/imAnesYT/Textura-Lib" alt="License"></a>
  <a href="https://pepy.tech/project/textura"><img src="https://pepy.tech/badge/textura" alt="Downloads"></a>
  <a href="https://www.python.org/"><img src="https://img.shields.io/badge/python-3.6%2B-blue.svg" alt="Python"></a>
</p>

---

## 📦 Installation

Install Textura from PyPI:

```bash
pip install textura
```

## 🔧 Usage
```python
import textura
from textura import Fore, Back, Style, txtra_print, txtra_format, option, colors_list, PrintError

# Set options (reset text at end, and prevent styled text in print())
option(resetend=True, strict=True)

# Display available colors and styles
print("Available styles and colors:")
colors_list()

print("\n--- Styled Print Examples ---\n")

# Foreground color example
txtra_print("{Fore.GREEN}Green text")

# Background color example
txtra_print("{Back.YELLOW}{Fore.BLACK}Black on yellow")

# Style example
txtra_print("{Style.BOLD}Bold text")
txtra_print("{Style.UNDERLINE}Underlined text")
txtra_print("{Style.ITALIC}Italic text")

# Combined styles
txtra_print("{Back.RED}{Fore.WHITE}{Style.BOLD}Bold white on red background")

# Using txtra_format to return a styled string
formatted = txtra_format("{Fore.LIGHTBLUE}{Style.UNDERLINE}Underlined Light Blue")
print(formatted)  # This works fine

# Incorrect usage: using styled text directly with print (strict=True will raise PrintError)
try:
    print("{Fore.RED}This should raise an error if strict=True")
except PrintError as e:
    print(f"Caught PrintError: {e}")
```
