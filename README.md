# Validating an Email with Regex

This tutorial will walk explain the regex functionality to validate an email address using the expression: 

`/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

For an overview of all regex components here's a handy [cheatsheet](https://medium.com/factory-mind/regex-tutorial-a-simple-cheatsheet-by-examples-649dc1c3f285). 


## Summary

Regular expressions (regex or regexp) are a sequence of characters that define a search pattern. Regular expressions are extremely useful in extracting information from any text by searching for one or more matches of a specific search pattern, and are commonly used to find or replace characters within a string or validate inputs. This tutortial will walk through the components of a regex using a common regex that validates email addresses.

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

### Anchors
The anchor `^` searches for any string starting with what follows the anchor, in the case of the email validator regex, that would be any string that begins with `([a-z0-9_\.-]+)`. Our regex also ends with a common anchor `$` which matches any string ending in what precedes that anchor, in this case `([a-z\.]{2,6})`.

The entire expression is surrounded by two backslashes, which we'll get to when we discuss flags, but are indicated by `/(regex)/` and potentially a letter outside of the backslash; when evaluating a regex, the anchors will be inside of the backslash characters.

### Quantifiers

This regex uses the `+` quantifier, which indicates that the first part of the string must be followed by 1 or more of what immediately precedes the `+`. In our expression, this quantifies at least 1 or more characters of `[a-z0-9_\.-]` before the `@` and `.`; this is standard email format of "character @ somewebsite . domain". 

The domain is specifically quanfied with the curly brackets of `{2,6}`, which further defines that the  preceding character set `[a-z\.]` will be between two to six characters only.

### OR Operator

OR operators are employed through the use of square brackets in the expression that indicate the place of any one character for which we're unsure what we're searching. For our email, this means the first part can be looking for any, at least one, character `a-z0-9_\.-` which is followed by @ and searching for any character `\da-z\.-`, followed by a period, searching for any character `a-z\.` only two to six times.

This is not the only way to indicate OR, but is the only OR operator used within this email expression.

### Character Classes

`\d` is used to match a single character that is a digit 0-9. Used within the OR operator, it is merely providing that one of the characters in the second part of an email between the `@` and `.` could possibly be a single digit.

### Flags

A regex usually comes within two backslash characters, and at the end we can specify a flag outside of these characters. There are no flags on this email validator regex.

### Grouping and Capturing

Groups are denoted within parenthesis `()`, in this case, we can see three groups:
`([a-z0-9_\.-]+)` for the first part of the email, usually personalized
`([\da-z\.-]+)` for the second part of the email, usually a website or domain name
`([a-z\.]{2,6})` for the third and last part, looking for a .org or .com type conclusion

### Bracket Expressions

Bracket expressions indicate OR values, discussed above.

### Greedy and Lazy Match

From the Medium cheatsheet linked above, "quantifiers ( * + {}) are greedy operators, so they expand the match as far as they can through the provided text". This expression uses both `+` and `{}`, which "greedily" matches by evaluating the expression at every character position in the string, if there's no match, it moves on to the next character and evaluates from that next position. 

### Boundaries

This regex contains no boundaries of `\b` or `\B` which would perform whole word searches.

### Back-references

This regex contains no back references to any character groups. 

### Look-ahead and Look-behind

This regex contains no look aheads or look behinds that evaluate the regex against the ahead or behind character not a part of the regex itself.

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)