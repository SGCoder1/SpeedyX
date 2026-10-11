---
title: Extern Modifier
parent: Keywords
layout: default
---

## `extern` Keyword

Tells the compiler that the function being called is implemented elsewhere, be it another object file or an entire library.
Support and capabilities are not finalized, but work as intended. If the compilation unit contains an external declaration,
resolution is handed off to the linker. **All external declarations defined must have the `global` modifier.**

{: .note }
If creating an implementation in assembly, your label must be mangled and match with the function signature.
The mangling is not officially standardized for the utilities yet and is subject to change.