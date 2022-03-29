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

> Every piece of knowledge must have a single, unambiguous, authoritative representation within a system.

This is one of the simplest coding principles. Its only rule is that code should not be duplicated. Instead of duplicating lines, find an algorithm that uses iteration. DRY code is easily maintainable. You can take this principle even further with model/data abstraction.

The cons of the DRY principle are that you can end up with too many abstractions, external dependency creations, and complex code. DRY can also cause complications if you try to change a bigger chunk of your codebase. This is why you should avoid DRYing your code too early. It's always better to have a few repeated code sections than wrong abstractions.

### KISS (Keep it simple, stupid)

> Most systems work best if they are kept simple, rather than made complicated.

The KISS principle states that most systems work best if they are kept simple rather than made complicated. Simplicity should be a key goal in design, and unnecessary complexity should be avoided.

### SoC (Separation of concerns)

> SoC is a design principle for separating a computer program into distinct sections such that each section addresses a separate concern. A concern is a set of information that affects the code of a computer program.

If you decide to go with this approach be careful not to split your app into too many modules. You should only create a new module when it makes sense to do so. More modules equals more problems.

### SOLID

> SOLID is a mnemonic acronym for five design principles intended to make software designs more understandable, flexible, and maintainable.

SOLID is extremely useful when writing OOP code. It talks about splitting your class into multiple subclasses, inheritance, abstraction, interfaces, and more.

* The Single-responsibility principle: "A class should have one, and only one, reason to change."
* The Open–closed principle: "Entities should be open for extension, but closed for modification."
* The Liskov substitution principle: "Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it."
* The Interface segregation principle: "A client should not be forced to implement an interface that it doesn’t use."
* The Dependency inversion principle: "Depend upon abstractions, not concretions."

## Code Formatters

Code formatters enforce coding style through automatic formatting and help to achieve and maintain clean code. Most of them allow you to create a style configuration file that you can share with your colleagues.

The most popular Python code formatters are:

* black
* flake8
* autopep8
* yapf

Most modern IDEs also include linters, which run in the background as you type and help to identify small coding mistakes, errors, dangerous code patterns and keep your code formatted. There are two types of linters: logical and stylistic.

The most popular Python linters are:

* Pylint
* PyFlakes
* mypy

## Naming Conventions

```
# This is bad
# represents the number of active users
au = 55

# This is good
active_user_amount = 55
```

## Variables

1. Use nouns for variable names

2. Use descriptive/intention-revealing names

```
# This is bad
c = 5
d = 12

# This is good
city_counter = 5
elapsed_time_in_days = 12
```

3. Use pronounceable names

```
from datetime import datetime

# This is bad
genyyyymmddhhmmss = datetime.strptime('04/27/95 07:14:22', '%m/%d/%y %H:%M:%S')

# This is good
generation_datetime = datetime.strptime('04/27/95 07:14:22', '%m/%d/%y %H:%M:%S')
```

4. Avoid using ambiguous abbreviations

```
# This is bad
fna = 'Bob'
cre_tmstp = 1621535852

# This is good
first_name = 'Bob'
creation_timestamp = 1621535852
```

5. Always use the same vocabulary

```
# This is bad
client_first_name = 'Bob'
customer_last_name = 'Smith'

# This is good
client_first_name = 'Bob'
client_last_name = 'Smith'
```

6. Don't use "magic numbers"

```
import random

# This is bad
def roll():
    return random.randint(0, 36)  # what is 36 supposed to represent?

# This is good
ROULETTE_POCKET_COUNT = 36

def roll():
    return random.randint(0, ROULETTE_POCKET_COUNT)

```

7. Use solution domain names

```
# This is bad
names = ["Nick", "Mike", "John"]

# This is good
score_list = [12, 33, 14, 24]
word_dict = {
    'a': 'apple',
    'b': 'banana',
    'c': 'cherry',
}
```

8. Don't add redundant context

```
# This is bad
class Person:
    def __init__(self, person_first_name, person_last_name, person_age):
        self.person_first_name = person_first_name
        self.person_last_name = person_last_name
        self.person_age = person_age


# This is good
class Person:
    def __init__(self, first_name, last_name, age):
        self.first_name = first_name
        self.last_name = last_name
        self.age = age
```

## Functions

1. Use verbs for function names

2. Do not use different words for the same concept

```
# This is bad
def get_name(): pass
def fetch_age(): pass

# This is good
def get_name(): pass
def get_age(): pass
```

3. Write short and simple functions

4. Functions should only perfmor a single task

```
# This is bad
def fetch_and_display_personnel():
    data = # ...

    for person in data:
        print(person)


# This is good
def fetch_personnel():
    return # ...

def display_personnel(data):
    for person in data:
        print(person)
```

5. Keep your arguments at a minimum

```
# This is bad
def render_blog_post(title, author, created_timestamp, updated_timestamp, content):
    # ...

render_blog_post("Clean code", "Nik Tomazic", 1622148362, 1622148362, "...")


# This is good
class BlogPost:
    def __init__(self, title, author, created_timestamp, updated_timestamp, content):
        self.title = title
        self.author = author
        self.created_timestamp = created_timestamp
        self.updated_timestamp = updated_timestamp
        self.content = content

blog_post1 = BlogPost("Clean code", "Nik Tomazic", 1622148362, 1622148362, "...")

def render_blog_post(blog_post):
    # ...

render_blog_post(blog_post1)
```

6. Don't use flags in functions

```
text = "This is a cool blog post."


# This is bad
def transform(text, uppercase):
    if uppercase:
        return text.upper()
    else:
        return text.lower()

uppercase_text = transform(text, True)
lowercase_text = transform(text, False)


# This is good
def uppercase(text):
    return text.upper()

def lowercase(text):
    return text.lower()

uppercase_text = uppercase(text)
lowercase_text = lowercase(text)
```

7. Avoid side effects

## Comments

| Type | Answers | Stakeholder |
| ---- | ------- | ----------- |
| Documentation | When and How | Users |
| Code Comments | Why | Developers |
| Clean Code | What | Developers |

1. Don't comment bad code, rewrite it

2. Readable code doesn't need comments

```
# This checks if the user with the given ID doesn't exist.
if not User.objects.filter(id=user_id).exists():
    return Response({
        'detail': 'The user with this ID does not exist.',
    })
```

3. Don't add noise comments

```
numbers = [1, 2, 3, 4, 5]

# This variable stores the average of list of numbers.
average = sum(numbers) / len(numbers)
print(average)
```

4. Use the correct types of comments

```
def model_to_dict(instance, fields=None, exclude=None):
    """
    Returns a dict containing the data in ``instance`` suitable for passing as
    a Form's ``initial`` keyword argument.
    ``fields`` is an optional list of field names. If provided, return only the
    named.
    ``exclude`` is an optional list of field names. If provided, exclude the
    named from the returned dict, even if they are listed in the ``fields``
    argument.
    """
    opts = instance._meta
    data = {}
    for f in chain(opts.concrete_fields, opts.private_fields, opts.many_to_many):
        if not getattr(f, 'editable', False):
            continue
        if fields is not None and f.name not in fields:
            continue
        if exclude and f.name in exclude:
            continue
        data[f.name] = f.value_from_object(instance)
    return data
```

5. Don't leave commented out code

## Decorators, Context Managers, Iterators, and Generators

### Decorators

### Context Managers

### Iterators

### Generators

## Modularity and Classes

## Testing
