# Hexidecimal Regex Tutorial

Hexidecimals are a way to store various types of data, such as color. They're also one of the most commonly used methods to detect color. You've probably seen some in a color wheel somewhere, typically looking something like "#FFFFFF"

## Summary

This tutorial will teach you how regular expressions in javascript for hexidecimals work (`/^#?([a-f0-9]{6}|[a-f0-9]{3})$/`), so you can use them in code for, say, detecting if the user puts a hexidecimal input into a GUI for a color selection.

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)

## Regex Components

### Anchors

Anchors are signifiers of a string, showing the requirements they must have. They come in two ways:

* the `^` anchor shows a string starting with the characters after it. It can be in two ways:

    * the exact method, which means the string must be exactly like the text like the anchor string. This method is achieved by just puttign the string after the `^`

    * the range method, which looks for specific matching characters. This is achieved by putting brackets after the `^`, such as `^[a-z]`. If we go back to our hexidecimal string, we can see a `[a-f0-9]`, showing that it must have any characters from a to f that must be lowercase or 0 to 9.

* the `$` anchor is exactly like the `^` anchor, except for text BEFORE it instead of text AFTER it.

* the `^` anchor can also turn a range into a negative range by putting it into the brackets, like so `[^gexGEX]`

### Quantifiers

Quantifiers set the limits of the match, or even a certain section of a string. 

There are many quantifiers, such as:

* The `*` quantifier, which says the pattern must match at least 0 times

* the `+` quantifier, which says the pattern must match at least 1 time

* the `?` quantifier, which says the pattern much match one or less times

* the `{}` quantifier, which sets a character limit. This can come in 3 ways:

    * `{ n }`, which detects if the pattern match exactly `n` times. If we look back to our hexidecimal regex, we can see a `{6}` and a `{3}`, which signify that the expressions they're for must match 6 and 3 times respectively.

    * `{ n, }`, which detects if the pattern match at least `n` times

    * `{ l, m }`, wich detects if the pattern match at least `l` times, and at most `m` times

### Grouping Constructs

Grouping constructs use `()` to group expressions together within the regex.

In the hexidecimal example, we can see that 2 expressions are grouped together, one that must be a character between a to f or 0 to 9 with 6 characters, and one that must be a character between a to f or 0 to 9 with 3 characters.

### Bracket Expressions

Bracket expressions were slightly discussed earlier, however, they still need to be fully explained. Bracket expressions are a set of brackets used to show the regex the set of characters it must match, such as `[a-f0-9]` in our example.

### Character Classes

Character Classes in regex, well, are just a shorter way to say a set of characters. It allows you to allow a set of characters in a regex without typing them out. 

Some character classes include:

* `.`, which matches any character except newline (`\n`)

* `\d`, which matches any numeral digit, this is basically a shorter way to say `[0-9]`

* `\w`, which matches any alphanumeric character, including `_`. This is basically a shorter way to say `[A-za-z0-9]`

* `\s`, which matches any whitespace character, such as tabs and line breaks

### The OR Operator

### Flags

### Character Escapes

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)
