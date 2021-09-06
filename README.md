## Regex Tutorial

What is **Regex**? Is it a dinosaur? Is it slang for rejects? In the world of programming, **Regex** is short for **Regular Expressions**. **Regex** are incredibly
useful for isolating information from bodies of text by search patterns. This tool is extremely versatile in that it can be used in almost
all programming languages. In this **gist**, we'll be analyzing an example of **Regex** in detail hoping to give users a better idea of
what it is and how to use it.

## Summary
```
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```
**The Regex above matches the character sequence of the example email below:**
```
email@hotmail.com
```
The code snippet above is an example of **Regex** that will be analyzed and explained in the following sections. This **Regex** is used to define
a sequence of characters that matches the pattern of an email address. A basic email address consists of 4 key properties:

- String of characters and/or digits and/or dots, hyphens and/or underscores before the @
- The "at" sign (@)
- The domain name which can be a string of characters and/or digits after the @ and before the dot (.)
- The domain extension preceeded by a dot (.)

The **Regex** example above will be split up and analyzed by component in the following sections. To help better understand the
information, the **Regex** can be read as 3 different strings compared to the example email:
```
([a-z0-9_\.-]+) can be read as "email"
```
```
([\da-z\.-]+) can be read as "hotmail"
```
```
([a-z\.]{2,6}) can be read as "com"
```

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Author](#author)

## Regex Components

### Anchors
The characters `^` and `$` indicate where the string begins and where it ends. With the given **Regex** examples, the `^` is attached
to `([a-z0-9_\.-]+)` which can be read as "email" or other text. The `$` is attached to `([a-z\.]{2,6})` which can be read as "com" or other extensions. This means that the string must begin with an "email" name (`([a-z0-9_\.-]+)`) and end
with a domain extension (`([a-z\.]{2,6})`).

### Quantifiers
The `{2,6}` towards the end of the **Regex** are known as **Quantifiers**, which put constraints on the length 
of an expression. This particular instance can be read as "atleast 2 characters, but no more than 6". For example, 
`{5,9}` would mean an expression could only be 5 to 9 characters in length.

The `+` in the "email" and "hotmail" expressions are also **Quantifiers**. The `+` means that the expressions
must have atleast one or more characters.

### Character Classes
In `([\da-z\.-]+)`, notice the `\d` within. The `\d` is known as a **Character Class**, which is notation that
matches any symbol from a certain set/class. In this instance, `\d` means any single-character digit between 0 and 9.

### Flags
Notice the `/` at the beginning and end of `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. These slashes mean
different things than the back slashes (\) used in **Character Classes**. These `/` are known as **Flags**, which are used to
define the boundaries of an expression (start point and end point). For example, if you moved the ending `/` to after the `@`,
nothing past the `@` will be included in the search pattern.

### Grouping and Capturing
Notice the parenthesis `()` in `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. These `()` create a 
**Capturing Group**. This operator is very useful when users need to extract information from strings or data. When 
there are multiple **groups** within a string,  the **groups** are stored and referenced individually in a database. For example,
if you removed the parenthesis from `([a-z\.]{2,6})` and extended the second group, only 2 groups would be created: 
`([a-z0-9_\.-]+)` and `([\da-z\.-]+\.[a-z\.]{2,6})`.

### Bracket Expressions
Notice the **brackets** `[]` inside `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. These **brackets** are used to define
sets of characters that can be used in different **groups**. For example, `a-z` and `0-9` can be read as "all characters in between".
When there are **brackets** surrounding a string, that means all characters/operators within are acceptable. For example, the 
characters **4** and **g** would be acceptable.

### Author
My name is **David Briagas**. I'm a Full-Stack Web Developer looking to expand my knowledge in the 
world of programming. You can view my full Github at [BriagasD98](https://github.com/BriagasD98).
