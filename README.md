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

The entire expression is surrounded by flags, which we'll get to in a moment, but are indicated by `/(regex)/` and potentially a letter. When evaluating a regex, the anchors will be inside of the flags.

### Quantifiers

This regex uses the `+` quantifier, which indicates that the first part of the string must be followed by 1 or more of what immediately precedes the `+`. In our expression, this quantifies at least 1 or more characters of `[a-z0-9_\.-]` before the `@` and `.`; this is standard email format of "character @ somewebsite . domain". 

The domain is specifically quanfied with the curly brackets of `{2,6}`, which further defines that the  preceding character set `[a-z\.]` will be between two to six characters only.


### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)