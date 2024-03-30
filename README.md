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

In javascript, the "or" expression is represented with the "pipe" symbol, aka `|`. The OR operator does exactly what you think it does, makes it have 2 conditionals that could be one of the other.

In the hexidecimal regex expresion, we see that `[a-f0-9]{6}` and `[a-f0-9]{3}` are seperated with the OR operator. This means it could either be a 6 character phrase using a to f and 0 to 9, or a 3 character phrase using the same characters.

### Flags

Flags are the one way a regex doesn't need to be inside slash characters. They are placed at the end of one, after the slash at the end. They define any other rules for the regex. There are 8 total flags.

* `d`, which generates a list of matching names for substring matches

* `g`, which makes it test against all possible matches

* `i`, which makes the match ignore case

* `m`, which allows `^` and `$` next to newline characters

* `s`, which allows `.` next to newline characters

* `u`, which treats the pattern as a sequence of unicode points

* `v`, which is just `u` with more unicode features

* `y`, which performs a "sticky" search that matches the current position in the target string
 
### Character Escapes

Character escapes ways to, well, "escape" characters that would otherwise be seen as a special command. This character, `\`, can make `{` seen as a normal character by putting `\{` in the regex.

## Author

Created by: Seth Correa (Seth The Furboi).

[Github](https://github.com/SethTheFurboi)
