# Comments-Format

An informal format for comments.

## Basic format

All text of the comment is to be wrapped in square brackets `[]`,
and must have a space after the comment token.

### example (Comment token is `#` in python):
```py
# [This a Comment but it is basic]
```

## Comment Syntax
A basic comment with no intent(eg: permission, question, etc) shall end with a period and a square bracket "`.]`"
A comment may use proper punctuation but is not bound to. 

### example (Comment token is `#` in python):
```py
# [This a Comment but it is basic.]
```

### Multiple Inline Comments
All comment tokens should be in the same column, and text characters shall be aligned in the same column.

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
