# Comments-Format

An informal format for comments.

**example** (This is a bloated comment and is not uniform in type hinting)
```py
# !TODO:inImplentation: [Make _list_(Connection) a _deque_ and change _meth_(pop) to :meth:`popleft`]
```

## Basic format

All text of the comment is to be wrapped in square brackets `[]`,
and must have a space after the comment token.

### example (Comment token is `#` in python):
```py
# [This a Comment but it is basic]
```

## Comment Syntax
A comment may use proper punctuation but is not bound to. restructured Text and some markdown can be used.
There may not be another square bracket in the commment, but you shall include it if unavoidable(think names, language syntax like subscripting)
as it affects Readability.

`|` delimiter signifies a new line in a single line.
`--` marks some code with a note this shall be at the end of a line if `|` delimiter is used.

### Multiple Inline Comments
All comment tokens should be in the same column, and text characters shall be aligned in the same column.
You can End the previous line with a semicolon to comment the line below.
### example (Python)
```py
class VeryGood:
    def __init__(self, Goodness: int):
        self.goodness = Goodness    # [This sets the attribute goodness,
        self.foo = "bar"            #  I dont think this code can be optimized;
        self.unexplainable = "UMMM" #  You can End the previous line with a
                                    #  semicolon to comment the line below.
                                    #  This holds the string UMMM.]
```
### Code Markers
`--` is a Marker.

### example
```py
class VeryGood:
    def __init__(self, Goodness: int):
        self.goodness = Goodness
        self.foo = "bar"
        self.unexplainable = "UMMM" # --|TO REMOVE|
```

### Block Comments
Multiple inline comments shall be preferred but it depends on the language.
Each newline should be aligned such that the first character is aligned(i.e in the same column) with the first text character,
this doesn't refer to the comment token or square bracket, etc.

### example (Block comments start with `/*` in C (C99), C++, Go, Swift and JavaScript)
```C
/* [This is a Long Comment, it is long, veryy long.
*   Please align it like this, The block comment doesn't
*   refer to Docstring in python.]
*/
```
*note: the asterisk between lines is not necessary it is used to show how to align the text*

## Communicating Intent
TODO, DESC (description), REASON, REQ can be used to specify the *type* of the comment, these *types* should strictly be typed in capital letters.
The types are succeeded by a `::` double colon token followed by a space.
The Text shall be aligned accordingly.
**Multiple intents** shall be seperated with `|` delimiter.

### Example
```py
# TODO:: [Implement the add function] | REASON:: [To refactor code]
```
```py
# REASON:: [Earlier version was slower]
```
```py
# DESC:: [Adds a list's element to another list's
#         elments given len(list1) == len(list2)]
```
```py
# REQ:: [Can we use an deque instead?]
```
### Specifying Staus or Marking an Comment
A comment can be marked by writing in lowercase between the two colon's. The marker's length shall be preferably less than 16 characters long.
```py
# TODO:low: [Implement Rudeness level attribute]
```
```py
# REQ:accepted:TODO:medium: [Implement __enter__ and __exit__]
```
### Type hinting in comments
The type as it is in the language surrounded by single underscores. i.e `str` becomes `_str_` & `null` -> `_null_`.
Some of the types that can be used are `_func_`, `_var_`, `_list<str>_`(list of strings), `_func<func, list>_` (a function which takes the following parameters)
Do not type hint too much and use basic type hinting like so: `_func_(add)`, `_var_(index)`, `_list_(connections)`.
Though it's best to type hint in the code if possible.
```py
# REQ:: [Add _func<int>_(IntToString) I do not know how to implement it]
.
.
.
# TODO:: [Remove VeryGood._attr_(foo)] | REASON:: [It's BAR]
# TODO:: [Add VeryGood._meth_(bar) returning "bar"]
# TODO:: [Add :meth:`foo` returning "FoO"]
```
### Importance and Permission
Importance is signified by `!` the more exclamtion signs the more urgent.
```py
# !!TODO:: [Patch ValueError on SOmethi...]
```
Permission is signified by `?`
```py
# ?TODO:granted: [Remove :func:`foo`]
```
### Specifying the Author
Comments needn't specify the author and preferably shall be anonymous(though not completly, as in modifying the git history).
It is assumed that a comment's author can be found from the git commit history, there also are extension such as gitlens to supplement this.
nonetheless the author is specified by an `@` outside the bracket block, surrounded by `<>`.
```py
# @TEEN-BOOM:TODO:: [Do Stuff]
```
```py
# TODO:: [Do Stuff]<@TEEN-BOOM>
```
```py
# TODO:: [stuff]<@TEEN-BOOM, @SOMEONE>
```
```py
# @TEEN-BOOM, @SOMEONE:TODO:: [stuff]
```
### Custom Intents, signs(i.e `!` and `?`) and acronyms or Format
You must specify custom intents, signs, and acronyms in a `comments.format` in the following manner, located in the the root.
You may change the Url if you are using a custom format
```
==============================
Format      | @Author(s):INTENT:status: [Text]<@Author(s)>
Typing      | "_Type<SubType>_" & ReStructuredText
AllowedText | "utf-8" & ReStructuredText & markdown
==============================

Signs:
==============================
    "*" | important
==============================

Intent Acronyms:
==============================
    "FUT" | The future goals
    "ADD" | To ADD
==============================

Status Acronyms:
====================================
    "den" | denied
    "abn" | idea abandoned for now
    "acc" | Accepted
========================================
 = Comment Format used <https://github.com/TEEN-BOOM/Comments-Format/README.md>
========================================
Any Notes regarding commenting.
```
*You may leave the last line blank if you dont have any notes*
