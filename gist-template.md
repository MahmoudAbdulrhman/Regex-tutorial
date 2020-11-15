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

#### Examples:

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

Character Classses(Character Set) tells the regex engine to match only one out Serveral specifiv character, such as digits, words, or whitespace.

#### Examples of Character Classes are as follows:

* `\d` - Matches a single character thea is a digit.
* `\w` - Matches a word character (any alphanumeric character plus underscore).
* `\s` - Matches a whitespace character (including tabs and line brakes).
* `.` - Matches any character.
* the capital casr for any Aformentioned characters will inverse the match.

#### Examples:

```
- \d Matches a single any digit 0-9.
- \w Matches a single any charcacter that is a-z.
- . Matches any character.
- \D Matches a single non-digit character.
- \W Matches a single any non-character that is a-z
- \s matches a single non-''.
```

### Flags

Flags are optional parameters that we can add to plain expression to make it search in a different way. Each flag is denoted by a single alphabetic character, and serves different purposes in modifying the expression`s searching behavior.

#### Examples of Flags are as follows:
* `g` -Globlal, does not return after the first match,which restarted any subsequest searches from the end of the previous match (Make the expression search for all occurences).
* `m` -Multi-line, when enabled  the Anchors (^$) will match the start and end of a line, rather than the whole string.
* `i` Insensitive, makes the entire expression case-insensitve.

#### Examples:

```
- /Hello/g Matches all `Hello` in the test.
- /Hello/m Matches the beginning and ending of each line woth `Hello`,rather than the whole string `Hello` itself.
= /Hello/i Matches all `hello` despite casre (Hello,hEllo,heLlo,HellO,hello,HELLO all match).
```

### Grouping and Capturing

Grouping unifies a pattern or string so that it is matched in a complete block

#### Examples of Grouping are as follows:

* `()` - parentheses creates a capture group.
* `(?:)` - using `?:` disables the capturing group.
* `(?<>)` - using `?<>` puts a name to the group

#### Examples:

```
- x(yz) parentheses create a capturing group with value yz.
- x(?:yz)* using ?: we disable the capturing group.
- x(?<bar>yz) using ?<bar> we put a name to the group.
```

### Bracket Expressions

Bracket Expressions are characters enclosed by a bracket `[]` matching any single character within the brackets.

*note: if the first character within the brackets is a `^` then it signifies any chracter **not** in the list, and is unspecified whether it matches an encoding error.

#### Examples of Bracket Expressions are as follows:

* `[]` - matching any single character within the brackets.
* `[]%` - matching the string inside the brackets before the `%` .
* `[^]` - matching any string that has not a letter from within the brackets (negation of expression).

#### Examples:

```
- [xyz]  matches a string that etiher has x or x y or x z (same as x|y|z).
- [x-y] similar to case above.
- [u-zU-Z0-9]   a string that represents a single hexadecimal digit, case insensitively.
- [0-9]% a string that has a character from 0-9 before a % .
- [^a-zA-Z]     a string that has not a letter from a to z or from A to Z.
```
### Greedy and Lazy Match

Greedy and/or Lazy Matching are quantifies that expand the match as far as possible through the text.

#### Examples of Greedy and/or Lazy Matching are as follows:

* `* + {}` - any one of these character can be used as a quanitifer for a Greedy or Lazy Match.

#### Examples:
```
- <.+?> matches any character that is one or more times included inside `<` and `>`, and expands as needed.
- <[^<>]+>  matches any character expects `<` or `>` one or more times included inside `<` and `>`.
```

### Boundaries

Not to be confused with actual characters, simply put, Boundaries are the places between characters. A Boundary should be thought of as a wall between any adjacent characters.

There are two types of Boundaries, **Word** and ***Non-Word**, each denoted by a specific character.

#### Examples of Boundaries are as follows:

* `\b` - A position that bounds a word, or where a word starts or ends. It denotes a place between a word and non-word character, at the start and end of a string.
* `\B` - Exact opposite of a word boundary, the negation of `\b` and will match **any position a word boundary doesnt.** *
* `*`Will match between a word and word character, as well as between a non-word and non-word character.

#### Examples:
```
- Hello World` has 12 total Boundaries with 8 Word Boundaries as seen below:
|H|e|l|l|o| |W|o|r|l|d|
^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^ ^
- N W W W W N N W W W W N  -  N = Nonword Boundary \ W = Word Boundary
- \bxyz\b matches a "whole words only search" for the string `xyz`.
- \Bxyz\B matches only if the pattern is fully surrounded by word characters `txyzt` would match the string `xyz` because it only has word boundaries.
```

### Back-references.

When using Grouping (look above) you may Capture the Group, which is saved in memory for later use. Backreferencing is the name given to the action of using these matches.
Back-referencing is the refernce of a captured match, save in memory, by a captured group.

#### Examples:
```
- ([xyz])\1 using \1 it matches the same text that was matched by the first capturing group.
- [uwx])([yz])\2\1 we can use \2 (\3, \4, etc.) to identify the same text that was matched by the second (third, fourth, etc.) capturing group.
- (?<bar>[xzy])\k<bar> we put the name bar to the group and we reference it later (\k<foo>). The result is the same of the first regex.
```

### Look-ahead and Look-behind

Look-ahead and Look-behind (lookaround) are `start and end` zero-length assertions [Anchors](#anchors) but they actually match characters, then ends the match, returning only the result: **Match or No Match**. They do not cosume characters in the string, but only assert wether a match is possible or not. Lookaround allows you to create regular expressions that are impossible to create without them, or that would get very longwinded without them.

#### Examples of Look-ahead and Look-behind are as follows:

```
- h(?=t) matches a h only if is followed by t, but t will not be part of the match.
- (?<!t)h matches a h only if is not preceded by an t, but t will not be part of the match.
```
## Author

Mahmoud Abdulrhman is a Junior Developer 
studying at UCB coding bootcamp

[GitHub Profile](https://github.com/MahmoudAbdulrhman)
