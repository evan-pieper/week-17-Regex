# A Basic Introduction to Functional Regular Expressions

In basic terms, regular expressions are patterns used to match character combinations in strings. They provide a powerful tool for searching, replacing, and parsing text with complex criteria. They use a blend of special characters and constructs to define search parameters. This document will seek to explain how regular expressions can be used to perform a variety of tasks, including matching a hexadecimal color code.
In web development, colors are often represented using hexadecimal notation. This document delves into a regular expression specifically designed to match hexadecimal color codes, which can be either 3-digit or 6-digit long, and may or may not start with a ‘#’. The regex that performs this operation is as follows:
```
 /^#?([a-f0-9]{6}|[a-f0-9]{3})$/.
```
This document will explain each component of this regex and how it works to match a hexadecimal color code.

## Summary

This article seeks to inform the user of the basic components of a regular expression and how they can be used to match character combinations in strings. It will cover the following topics: anchors, quantifiers, grouping constructs, bracket expressions, character classes, the OR operator, flags, and character escapes. 

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
There are two basic types of regex characters. Literal characters are the simplest. They are characters that match only and exclusively themselves. For example, the regex /d/ will match the character ‘d’, but not the character 'D'. The other type of component is a metacharacter. Metacharacters are special characters that have a unique meaning within a regular expression. For example, the regex /./ will match any character except for a newline. The \d metacharacter matches any digit character, and the \w metacharacter matches any alphanumeric character.

### Anchors
In the regex 
```
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
```
, the ^ and $ characters are anchors. The ^ character asserts the position at the start of a line, and the $ asserts the position at the end of a line. Together, they denote a string of characters or quantifiers that must be matched exactly. In this case, the ^ and $ characters are used to ensure that the regex matches the entire string, and not just a substring.

### Quantifiers
The ? in #? is a quantifier that matches 0 or 1 occurrence of the preceding element, making the ‘#’ optional. {6} and {3} are also quantifiers, matching exactly 6 and 3 occurrences of the preceding character classes respectively.

### Grouping Constructs
( and ) are used to create a capturing group. This groups the 6-digit and 3-digit patterns together, allowing the OR operator | to work correctly. The capturing group also allows the regex to return the matched hex code, rather than the entire string.

### Bracket Expressions
[a-f0-9] is a bracket expression that matches any single character from the set of characters defined inside the brackets. In this case, it matches any digit or lowercase letter from ‘a’ to ‘f’.

### Character Classes
The regex doesn’t use any predefined character classes, but [a-f0-9] forms a custom character class. Character classes are used to match a single character from a group of characters. In this case, the character class matches any digit or lowercase letter from ‘a’ to ‘f’.

### The OR Operator
| is the OR operator. It allows for the matching of either the 6-digit pattern [a-f0-9]{6} or the 3-digit pattern [a-f0-9]{3}. The OR operator is used to match either pattern, but not both.

### Flags
There are no flags specified in the regex. However, if case-insensitivity is desired (to match uppercase letters as well), the ‘i’ flag can be added. For example, the regex: 
```
/^#?([a-f0-9]{6}|[a-f0-9]{3})$/i
```

### Character Escapes
There are no character escapes in the regex. However, if the user wants to match a literal character that is also a metacharacter, they can use a backslash to escape it. For example, the regex: 
```
/^\d+$/
```
will match any string of digits. The + metacharacter matches 1 or more occurrences of the preceding element. In this case, it matches 1 or more digits. If the user wants to match a literal ‘+’ character, they can use the regex: 
```
/^\d\+$/
```
The backslash escapes the ‘+’ character, allowing it to be matched literally.

## Author

Evan Pieper is a full-stack web developer with a background in education and environmental science. If you would like to check out more from this author, please visit their [GitHub](https://github.com/evan-pieper)
