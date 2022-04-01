# URL Regex Piece by Piece

Per Marijn Haverbeke, who is the author of Eloquent Javascript, "Regular expressions 
are a way to describe patterns in string data. They form a small, separate language 
that is part of JavaScript and many other languages and systems."

## Summary

Below is an regex example to match a URL:
/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/

These tags are made up of regular expressions a.k.a. regex. Regex are specific characters
used in a sequence in order to define a specifc search pattern. Regex characters have a 
lot of components to them. Let's take a deeper look at the above expression. 

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Character Classes](#character-classes)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)

## Regex Components

### Anchors
Anchors do not match any character at all. Instead, they match a position before, after, or between characters.
  (^)          =  The caret is an anchor the matches the beginning of an input
  ($)          =  The dollar sign is also an anchor, but it matches the end of an input string

### Quantifiers
Quantifiers specify how many instances of a character, group, or character class must be present in the 
input for a match to be found. In the regex URL they are used in the following areas:
  https?       =  This matches 'https', 'http' (the ? after the https is only targeting the letter 's';                         meaning it is going to match weather the 's' is there or not.)
  [\da-z\.-]+  =  This part of the expression matches a single digit(\d), a group of letters (a-z), dot 
                  (.) or hyphen (-) 1 or more times
  [a-z\.]{2,6} =  This matches a minimum of 2 and a maximum of 6 copies of a sequence [a-z\.]
  [\/\w \.-]*  =  This matches (\/\) any forward slash, (\w \.-) matches any alphanumeric character, the '.',                   and '-', which can match "www", "//", "-" hyphens, "." and periods

### Character Classes
Character Classes are used so a given sequence of characters matches a larger set of characters.

  [a-z]       =  Used to match lowercase alphabetic characters between a and z
  \w          =  Used to match an alphanumeric character("word character")
  \d          =  This matches any digit character
  .           =  This matches any character except for a new line

### Grouping Constructs
The use of Grouping constructs is to delineate the subexpressions of a regular expression and capture the 
substrings of an input string. For example in the URL regex we can see 4 kinds:
  (https?:\/\/)  =  To match: ' ', 'https://', 'http://'
  ([\da-z\.-]+)  =  To match: 'ab.c-7', 'ab'
  ([a-z\.]{2,6}) =  To match: 'ab.', '.ca'
  ([\/\w \.-]*)  =  To match: '/', '/ab.'

### Bracket Expressions
Bracket Expressions can math a list expression or a non-matching list expression. These expressions consists 
of one or more expressions: ordinary characters, collating elements, collating symbols, equivalence classes, 
character classes, or range expressions. We can find 3 in the URL regex:
  [\da-z\.-]
  [a-z\.]
  [\/\w \.-]

## Author

Gino Colman
* [Email](mailto:gdcolman95@gmail.com)
* [Gist](https://gist.github.com/ginocorp/f404a37492aa8a53bd8636434865dec6)
* [Github](https://github.com/ginocorp)