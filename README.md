# TokenVector Language Support

[![Marketplace Version](https://img.shields.io/vscode-marketplace/v/nguyenhungtran18.tokenvector-syntax?style=flat-square&color=blue&label=Marketplace)](https://marketplace.visualstudio.com/items?itemName=nguyenhungtran18.tokenvector-syntax)
[![Installs](https://img.shields.io/vscode-marketplace/d/nguyenhungtran18.tokenvector-syntax?style=flat-square&color=success&label=Installs)](https://marketplace.visualstudio.com/items?itemName=nguyenhungtran18.tokenvector-syntax)
[![Rating](https://img.shields.io/vscode-marketplace/r/nguyenhungtran18.tokenvector-syntax?style=flat-square&label=Rating)](https://marketplace.visualstudio.com/items?itemName=nguyenhungtran18.tokenvector-syntax)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](LICENSE)
[![.NET 8](https://img.shields.io/badge/.NET-8.0%20LTS-purple.svg?style=flat-square)](https://dotnet.microsoft.com/)

Official VS Code language support for **TokenVector (`.tkv`, `.tv`)** — an Ahead-Of-Time (AOT) compiled, statically-typed programming language targeting .NET CIL with unboxed scalar types, zero external runtime dependency, and zero-allocation memory performance.

![TokenVector Syntax Preview](https://raw.githubusercontent.com/nguyenhungtran18/tokenvector-grammar/main/images/preview.png)

---

## ⚡ Quick Start (3 Easy Steps)

Get up and running with TokenVector in less than 2 minutes:

### 1. Install Extension
Search for **`TokenVector Language Support`** in the VS Code Extensions Marketplace (`Ctrl+Shift+X`) and click **Install**.

### 2. Write Your First Program (`hello.tkv`)
Create a new file `hello.tkv` and type `tkv-entry` + `Tab` (or write the code below):

```tokenvector
# -*- coding: utf-8 -*-
# hello.tkv - First Native TokenVector Application

def calculate_sum(a: "i32", b: "i32") -> "i32":
    return a + b

def run() -> "str":
    print("=== TokenVector Native Application Initialized ===")
    a = 15
    b = 25
    c = calculate_sum(a, b)
    print("Computed Result a + b = " + str(c))
    return "SUCCESS"
```

### 3. Download Compiler `tkvc.exe` & Run Native Binary

1. **Clone the official TokenVector repository** to obtain `tkvc.exe` and standard libraries (`stdlib`):
   ```powershell
   git clone https://github.com/nguyenhungtran18/TokenVector.git
   ```

2. **Compile directly to a standalone native PE executable (`.exe`)**:
   ```powershell
   # Compile standalone source code
   ./tkvc.exe hello.tkv --out hello.exe --entry run

   # Or compile with numerical tensor library TokenVector.Numerics
   ./tkvc.exe main.tkv -r TokenVector.Numerics.dll -o main.exe
   ```

3. **Run standalone binary**:
   ```powershell
   .\hello.exe
   ```

**Console Output:**
```text
=== TokenVector Native Application Initialized ===
Computed Result a + b = 40
SUCCESS
```

* **Binary Footprint:** Only **8.5 KB** with zero external Python runtime dependencies and True No-GIL multithreading.

---

## ✨ Features

- **🎨 Rich Syntax Highlighting:**
  - **Keywords & Control Flow:** `def`, `class`, `return`, `if`, `elif`, `else`, `for`, `while`, `import`, `from`, `with`, `yield`, `async`, `await`, `lambda`, `raise`, `try`, `except`, `finally`, `pass`, `break`, `continue`.
  - **Unboxed Scalar Types:** `i8`, `i16`, `i32`, `i64`, `u8`, `u16`, `u32`, `u64`, `f16`, `f32`, `f64`, `str`, `int`, `float`, `bool`, `void`, `TkvInt`, `TkvStr`.
  - **Compiler Identifiers:** `__name__`, `__file__`, `self`.
  - **Functions, Classes & Records:** Full lexical highlighting for definitions, method calls, typed class fields, and inheritance.
  - **Operators & Literals:** Arithmetic, in-place assignments, comparison, arrow notation (`->`), hex and floating-point numbers.

- **⚡ Productivity Code Snippets:**
  - `tkv-entry` → Boilerplate application entry point (`run()` function).
  - `tkv-func` → Function declaration with unboxed type annotations.
  - `tkv-class` → Class definition with typed fields and methods.

- **📐 Smart Indentation & Bracket Matching:**
  - Automatic 4-space indentation following block headers (`def`, `class`, `if`, `elif`, `else`, `for`, `while`, `try`, `except`).
  - Auto-closing pairs for `{}`, `[]`, `()`, `""`, `''`.

---

## 💻 Code Example: Object-Oriented Class with Typed Fields

```tokenvector
# -*- coding: utf-8 -*-
# vector.tkv - 2D Vector Calculation in TokenVector

class Vector2D:
    x: "f64"
    y: "f64"

    def __init__(self, x, y):
        self.x = x
        self.y = y

    def magnitude_squared(self) -> "f64":
        return self.x * self.x + self.y * self.y

def run() -> "str":
    v = Vector2D(3.0, 4.0)
    mag_sq = v.magnitude_squared()
    print("Vector2D magnitude squared: " + str(mag_sq))
    return "SUCCESS"
```

---

## 🏛️ Ecosystem & Official Repositories

- ⚡ **TokenVector Compiler & Standard Library:** [https://github.com/nguyenhungtran18/TokenVector](https://github.com/nguyenhungtran18/TokenVector)
- 🔢 **TokenVector.Numerics Mathematical Core Engine:** [https://github.com/nguyenhungtran18/TokenVector.Numerics](https://github.com/nguyenhungtran18/TokenVector.Numerics)
- 🎨 **TokenVector VS Code Extension:** [https://marketplace.visualstudio.com/items?itemName=nguyenhungtran18.tokenvector-syntax](https://marketplace.visualstudio.com/items?itemName=nguyenhungtran18.tokenvector-syntax)

---

## 📋 Scope & Configuration

- **Language ID:** `tokenvector`
- **File Extensions:** `.tkv`, `.tv`
- **Scope Name:** `source.tokenvector`
- **Compiler Toolchain:** `tkvc.exe` (TokenVector Compiler)
- **Official Repository:** [https://github.com/nguyenhungtran18/TokenVector](https://github.com/nguyenhungtran18/TokenVector)

---

## 🤝 Contributing & Feedback

Contributions, bug reports, and syntax suggestions are welcome on the [TokenVector GitHub Repository](https://github.com/nguyenhungtran18/TokenVector).

---

## 📄 License

[MIT License](LICENSE) © 2026 TokenVector Project / Nguyen Hung Tran.
