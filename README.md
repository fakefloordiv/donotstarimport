# Do not star import!
---
## What is star import?
Star import is a type of import that imports all the variables from library (or, if presented, from `__all__` tuple in a global scope). The syntax looks like `from something import *`
## Why is it bad?
It is too implicit. When you're looking in a code where star import was used, you cannot be sure whether some function or variable defined somewhere below, or was imported from some module. In case of 2+ star imports, you can multiply this problem by 3, as at this point you can't know even which module it was imported from
## But I saw usage of star imports in good projects
Yes, star imports has their usecase. For example, in `__init__.py` file. In this case star import is justified, but even in this case it's better to define some `__all__` tuple with variables names to export
## So how to know whether I can use it my code?
The problem is that star import is often used by newbiens that do not know how and when is it proper to use this construction, so I would recommend you to avoid using this thing in places where you can. Or, at least, add `__all__` variable to make autocompletion life's easier
