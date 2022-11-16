# Regex: Hex Color Values

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The regular expression I have chosen is for hexadecimal color values like those used in CSS files. There are currently 16,777,216 different colors available in HTML, so hexadecimal digits are used since they have a higher information density than decimal digits. Color values can be expressed in two varieties: normal hexadecimal values, like #4169E1 for Royal Blue, and shorthand versions, such as #00F for Blue. 00F is shorthand for 0000FF. Shorthand only works when both digits are the same in each duplet.

## Summary

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The regex for hexadecimal color values is: `/^#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3})$/`. This regex will search a text for any appearances of hex color values of both the longhand and shorthand versions, whether or not they include the pound sign in front.

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

### **Anchors**

The anchors `^` and `$` are used to specify the beginning and end of the string, respectively. These will ensure that only appearances of color values that are _not_ merely substrings of words will be returned.

### **Quantifiers**

In this snippet: `[a-fA-F0-9]{6}` the {6} specifies that the preceding character class should be repeated six times. In this one: `[a-fA-F0-9]{3}` it means the character class should be repeated three times. Normally, curly braces are in the following format: {min, max}, but when the comma and max are excluded, it searches for the exact number of repetitions of min. Also, the question mark in `^#?` means that the # literal can appear either 0 or 1 times.

### **Grouping Constructs**

This part of the regex: `([a-fA-F0-9]{6}|[a-fA-F0-9]{3})` is grouped together using parentheses. This is called a capture group and could be referenced using `\1` later in the same regex to search for the exact same pattern again.

### **Bracket Expressions**

`[a-fA-F0-9]` is a bracket expression. The brackets tell the regex engine to treat everything inside of them as one criterion.

### **Character Classes**

`[a-fA-F0-9]` is a character class inside a bracket expression. This shows the regex engine to search for _a single character_ that meets any of these criteria: lowercase letters from a to f, uppercase letters from A to F, or digits from 0 to 9.

### **The OR Operator**

`[a-fA-F0-9]{6}|[a-fA-F0-9]{3}` uses the OR operator in the form of `|`. Since RGB hex values can be written in three-digit form sometimes (i.e., the shorthand for 00FF00 is 0F0), the three-digit alternative is useful, even though it could potentially return three-letter words with letters from A to F.

## Author

https://github.com/nookworth
