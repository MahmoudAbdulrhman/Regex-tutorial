# Title Regex Tutorial

In this tutorial,we will be taking a brief look into what Regex (regular expressions) are and how they work. while regular expressions may seem to be overwhelming at first glance.
just like with any language, they can broken down into it`s most simple parts easily understood.  d

## Summary

Regex (short for regular expression) is a string that allows you to create search patterns that match, manage, and locate text. an example code snippt of regex as following:
```
/[\w._%+-]+@[\w.-]+\.[a-zA-z]{2,4}/
```
A regular expression used to match an e-mail address.

Regular expression can also be used from the commend line and within text-eitors to find within a file.

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

Anchors are characters within the regular expression that allow the user to match that begin with or ends with (or both) certain characters.

Exanples of Anchors are as follows:

* `^` - matches any string that start with the anterior word.
* `$` -matches a string that end with preceding word before the character.

#### Exaples:

```
- ^winnig  matches any string - with `winning`.
- World$ matches any string ending with `world`
- ^Hello World$ matches exact string 
```

### Quantifiers

Quantifiers are characters within the regylar expression that specify how many instance a character,group,or character must represented in the input to be matched.

Example of Quantitfers are as follows:

* `*` - matches a string that has the anterior followed be zero or more of last character.
* `+` - matches a string that has the anterior followed by one or more of last character.
* `?` - Matches a string that has the anterior follwoed by zero or one of the last charcater.
* `{}` - Matches a string that has the anterior followed by how ever many the number in the brackets of the last character in the string.
* `()` - Matches a stribg that has any anterior characters followed by zweo or more copies of the string within the brackets.

#### Examples:

```
- xyz* matches a string that has followed by zero or more z

- x yz+ matches a string that has xy followed by one or more z.

- xyz? matches a string that has xy followed by zero or one z.

- xyz{2} matches a string that has xy followed by 2 or more z.

- xyz{2,} matches a string that has xy followed by 2 or more z.

- xyz{2,5} matches a string that xy followed by 2 up to 5 z,

- x(yz)*  matches a string that has x followed by zero or more copiws of the sequence yz.

- x(yz)* matches a string that has x followed by 2 too 5 copies of the sequence yz.
```

### OR Operator

OR Operators (Alternation Operator) matches on of a choice of regular expressions: if you put the character(s) representing the alternation operator between any two characters in the regular expression, the result matches the union of the strings that those two characters match.

Examples of OR Operators are as follows:

* `(|) - Match a string that has any anterior characters followed by the characters on the left or right of the vertical bar.

* `[]` - Matches a string that has any characters without any characters within the brackets.

#### Examples
```
- x(y|z) Matches a string that has x followed by y or z (and captures y or z).
- x[yz] Matches a string that has x, but without capturing b or c.
```
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
