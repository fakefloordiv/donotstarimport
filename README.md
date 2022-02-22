# Do not star import!
---
## What is star import?
Star import is a type of import that imports all the variables from library's namespace (or, if presented, from `__all__` with any iterable value in a global scope). The syntax looks like `from something import *`
## Why is it bad?
It is too implicit. When you're looking in a code where star import was used, you cannot be sure whether some function or variable was defined somewhere below, or imported from some module. In case of 2+ star imports, you can multiply this problem by 3, as at this point you cannot even know which module it was imported from
## But I saw usage of star imports in good projects
Yes, star imports has their usecase. For example, in `__init__.py` file. In this case star import is justified, but even in this case it's better to define some `__all__` iterable (mostly presented as a tuple) with variables' names to export. For example: `__all__ = ("foo", "bar")`
## So how to know whether I can use it my code?
The problem is that star import is often used by newbiens that do not know how and when it is proper to use this construction, so I would recommend you to avoid using this thing in all the places where you can. Or, at least, define `__all__` variable to make autocompletion's life easier
