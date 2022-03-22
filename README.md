# Python Clean Code

* Easy to understand
* More efficient
* Easier to maintain, scale, debug and refactor

## Code Standards

### PEP 8 (Python Enhancement Proposal)

#### PEP 8 naming conventions:

* Class names should be CamelCase (`MyClass`)
* Variable names should be snake_case and all lowercase (`first_name`)
* Function names should be snake_case and all lowercase (`quick_sort()`)
* Constants should be snake_case and all uppercase (`PI = 3.14159`)
* Modules should have short, snake_case names and all lowercase (`numpy`)
* Single quotes and double quotes are treated the same (just pick one and be consistent)

#### PEP 8 line formatting:

* Indent using 4 spaces (spaces are preferred over tabs)
* Lines should not be longer than 79 characters
* Avoid multiple statements on the same line
* Top-level function and class definitions are surrounded with two blank lines
* Method definitions inside a class are surrounded by a single blank line
* Imports should be on separate lines

#### PEP 8 whitespace:

* Avoid extra spaces within brackets or braces
* Avoid trailing whitespace anywhere
* Always surround binary operators with a single space on either side
* If operators with different priorities are used, consider adding whitespace around the operators with the lowest priority
* Don't use spaces around the = sign when used to indicate a keyword argument

#### PEP 8 comments:

* Comments should not contradict the code
* Comments should be complete sentences
* Comments should have a space after the # sign with the first word capitalized
* Multi-line comments used in functions (docstrings) should have a short single-line description followed by more text

### Pythonic Code

* Variable tricks
* List manipulation (initialization, slicing)
* Dealing with functions
* Explicit code

#### Non-Pythonic:

```
n = 10
sum_all = 0

for i in range(1, n + 1):
    sum_all = sum_all + i

print(sum_all)  # 55
```

#### Pythonic:

```
n = 10
sum_all = sum(range(1, n + 1))

print(sum_all)  # 55
```

### The Zen of Python

```
>>> import this

The Zen of Python, by Tim Peters

Beautiful is better than ugly.
Explicit is better than implicit.
Simple is better than complex.
Complex is better than complicated.
Flat is better than nested.
Sparse is better than dense.
Readability counts.
Special cases aren't special enough to break the rules.
Although practicality beats purity.
Errors should never pass silently.
Unless explicitly silenced.
In the face of ambiguity, refuse the temptation to guess.
There should be one-- and preferably only one --obvious way to do it.
Although that way may not be obvious at first unless you're Dutch.
Now is better than never.
Although never is often better than *right* now.
If the implementation is hard to explain, it's a bad idea.
If the implementation is easy to explain, it may be a good idea.
Namespaces are one honking great idea -- let's do more of those!
```

## Code Principles

### DRY (Don't repeat yourself)

### KISS (Keep it simple, stupid)

### SoC (Separation of concerns)

### SOLID

## Code Formatters

## Naming Conventions

## Variables

## Functions

## Comments

## Decorators, Context Managers, Iterators, and Generators

### Decorators

### Context Managers

### Iterators

### Generators

## Modularity and Classes

## Testing