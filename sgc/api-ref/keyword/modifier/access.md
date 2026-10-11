---
title: Access Modifiers
parent: Keywords
layout: default
---

# Access Modifiers

{: .warning }
The access modifiers are not fully developed and its behavior is subject to change.


SGCode defines 3 access modifiers: `public`, `private`, `global`. They control the visibility of its type and members.

## `public` Keyword
Allows the type to be accessed from anywhere within the program. When combined with `global`, the type can be accessed
from other binaries, essentially exporting the type. To export types, you **must** compile as a reference library.

## `global` Keyword
Allows the creation of global fields or functions. This modifier can only be used on functions or fields outside
of a type. Missing this keyword otherwise will cause a compiler error. Global functions are `public` by default unless
specified `private`. In that case, it will only be accessible to the file it was created in.

## `private` Keyword
This is the least permissive access modifier. When applied to a field, it makes the type accessible only from within its type.