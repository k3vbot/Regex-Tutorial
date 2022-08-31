# Hexadecimal Color Code Regex Tutorial

Regex is short for Regular Expressions. They are sequences of character that are used to define search patterns in text. For example, our good friend ctrl + f allows us to search for specific words or characters in a document and will find us the direct matches. Regex can be used in a much more complex manner, allowing us to search for specific patterns and not simply 1 to 1 matches.  

## Summary

This tutorial will break down the regex for a hexadecimal color code. The expression is as follows: 

^#([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})$

Hex codes are in one of two formats. The standard hex triplet, which starts with # and has 6 alphanumeric characters after it, and the shorthand version, which starts with # and has 3 alphanumeric characters after. 

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

There are two anchors for Regular Expressions:

The beginning carrot: `^` and
The ending dollar sign: `$`

`^`#([A-Fa-f0-9]{6}|[A-Fa-f0-9]{3})`$`

### Quantifiers

Quantifiers are the number of characters that are used to find an exact match. Quantifiers can either be Greedy or Lazy. A Greedy quantifier tries to match as many times as possible with an element. Conversely, a Lazy quantifier tries to match as few times as possible. A Greedy quantifier can be turned Lazy by adding a `?`. The following are the Greedy quantifiers:
- `*` matches zero or more times
- `+` matches one or more times
- `?` matches zero or one time
- `{ n }` matches exactly n times
- `{ n ,}` matches at least n times
- `{ n , m }` matches from n to m times

As mentioned earlier, there are two hex color code formats. We will use the OR operator to distinguish which format we are using. in the Hex Value regular expression above we have `{6}` (Hex Triplet Format) and `{3}` (Shorthand Hex Format), this means that the length of the component preceding these quanitifiers should be 6 and 3. 

### Grouping Constructs

Grouping constructs delineate the subexpressions of a regular expression and capture the substrings of an input string. For grouping, we use parenthesis `()` around the subexpression we are looking for. For example, in the group `(ABC)`, every instance of the character `A` followed by `B` followed by `C` will be matched. 

In our hexadecimal color code we have one group being matched in between the parenthesis. 

^#`(`[A-Fa-f0-9]{6}|[A-Fa-f0-9]{3}`)`$

There are situations where there would be multiple groupings. Like in an email, where one group would be before the `@`, another after, and a third after the `.`

### Bracket Expressions

Bracket expressions `[]` can be used to match a single character or element. Bracket expressions signify the befinning of a character class or quantifier statement. In our example we are using the brackets to search for the character class `A-Fa-f0-9` in both the standard and shorthand format. 

### Character Classes

Character classes are descriptions inside the regular expression that informs us what type of characters to look for. In our example, our character classes are `A-Fa-f0-9`. This will search for any characters that are between the capital letters `A` through `F`, the lowercase letters `a` through `f` and the numbers `0` through `9`. 

^#([`A-Fa-f0-9`]{6}|[`A-Fa-f0-9`]{3})$

### The OR Operator

The OR operator indicates that either component within the expression could be the one that the expression should look for. It is defined by the `|` character. In our example, it says that the regex should look for the standard hex code OR the shorthand hex code. 

^#([A-Fa-f0-9]{6}`|`[A-Fa-f0-9]{3})$

### Flags

Flags can affect the search of regular expressions. There are six different types of flags: 
- `i` this flag makes the search non-case sensitive
- `g` this flag makes it so it will search for all matches, withouth it, it will only return the first result
- `m` this flag is called multiline mode. It only affects the behavior of `^` and `$`, allowing to search to cover multiple lines of text. 
- `s` this flag enables "dotall" mode, that allows a dot to match newline character
- `u` this flag enables Unicode support, enabling correct processing of surrogate pairs
- `y` this flag searches the exact position in the text. Also called "Sticky"

Our example has none of these flags. 

### Character Escapes

Character escapes are used to indicate a literal character. Certain letters that represent common character classes also escape, such as `\w` for a word charcter or `\s` for a space. 

Our example has no character escapes. 

## Author

Kevin Muehlbauer

Coding student at UC Berkeley Extension's Full Stack Coding Bootcamp.

Github: [k3vbot](https://github.com/k3vbot)

