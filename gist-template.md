# Regular expression (Regex) explained

## Summary

Regular expression (regex) is a sequence of characters that specifies a search pattern in any given text (string). In this tutorial we discuss how we can search through a text file to find an email address or verify if a given string is an email address. 

/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components
The RegEx we are dissecting today has three elements.

Element 1: Username ([a-z0-9_\.-]+)

This element will check to match the username portion of the email address. It may contain any letters, any numbers, periods, underscores, or dahses.

Element 2: Domain

This element will check to match the domain portion of the email address. It may contain letters, numbers and dashes.

Element 3: Suffix

this element checks the suffix fo the email address. It may contain only letters, and they must be between 2 and 6 characters long.
### Anchors
Anchors assert that the engine's current position in the string matches a well-determined location: for instance, the beginning of the string, or the end of a line.

In this example we use two anchors '^' at the beginning and '$' at the end to match the string. 
### Quantifiers
A regex quantifier tells the regex engine to match a certain quantity of the character, token or subexpression. In our example '+' tells the search engine to match tokens immediately to the left. (greedy match)

{2,6} define a minimum and maximum characters between 2 and 6 characters and return the result. 
### OR Operator
a(b|c) matches a string that has a followed by b or c (and captures b or c)
### Character Classes
With a character class, we can tell the regex engine to match only one out of several characters by placing between square bracket.
In our example \d matches a single character that is a digit
### Flags
A regex usually comes within this form /abc/, where the search pattern is delimited by two slash characters /. At the end we can specify a flag with these values (we can also combine them each other):

g (global) does not return after the first match, restarting the subsequent searches from the end of the previous match
m (multi-line) when enabled ^ and $ will match the start and end of a line, instead of the whole string
i (insensitive) makes the whole expression case-insensitive (for instance /aBc/i would match AbC)
### Grouping and Capturing
This operator is very useful when we need to extract information from strings or data using our preferred programming language.
Example:
a(bc)    parentheses create a capturing group with value bc
a(?:bc)*  using ?: we disable the capturing group 
a(?<foo>bc) using ?<foo> we put a name to the group 
### Bracket Expressions
[abc] matches a string that has either an a or a b or a c -> is the same as a|b|c 
in our example [\da-z\.-] matches string from a-z.
### Greedy and Lazy Match
The quantifiers ( * + {}) are greedy operators, so they expand the match as far as they can through the provided text.
In our example + is greedy match.

to make it lazy match we add ? 

<.+?> matches any character one or more times included inside < and >, expanding as needed. 
### Boundaries
The metacharacter \b matches at a position that is called a “word boundary”.
\babc\b performs a "whole words only" search
### Back-references
Backreferences match the same text as previously matched by a capturing group. If we want to match a pair of opening and closing HTML tags, and the text in between. By putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag.

Example
([abc])\1 using \1 it matches the same text that was matched by the first capturing group 
### Look-ahead and Look-behind
Lookahead allows to add a condition for “what follows”. Lookbehind is similar, but it looks behind. That is, it allows to match a pattern only if there's something before it.

Examples:
Look-ahead
d(?=r)  matches a d only if is followed by r, but r will not be part of the overall regex match

Look-behind
(?<=r)d matches a d only if is preceded by an r, but r will not be part of the overall regex match
## Author
Prepared by remish. for more info please visit my [GitHub](https://github.com/remishn)

