# TokenVector Language Support

Official TextMate Grammar and Language Configuration for **TokenVector (`.tkv`)**, a native compiled programming language targeting .NET CIL with zero-allocation scalar types.

## Features
- **Syntax Highlighting**: Full tokenization for keywords, CIL unboxed types (`i32`, `i64`, `f32`, `f64`, `str`, `int`, `bool`), special compiler macros (`__tkv_import__`, `__tkv_extern_assembly__`, `__tkv_entry__`), classes, functions, numbers, and strings.
- **Auto Indentation**: Automatic 4-space indentation rules following block headers (`def`, `class`, `if`, `elif`, `else`, `for`, `while`, `try`, `except`).
- **Auto Closing Pairs**: Automatically inserts matching braces `{}`, brackets `[]`, parentheses `()`, and quotes `""`, `''`.

## Scope Information
- **Scope Name**: `source.tokenvector`
- **File Extensions**: `.tkv`
- **Repository**: [https://github.com/nguyenhungtran18/TokenVector](https://github.com/nguyenhungtran18/TokenVector)

## License
MIT
