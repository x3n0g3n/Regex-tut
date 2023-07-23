# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary
A Regex, or regular expression, is a type of object that is used to help you extract information from any string data by searching through text to find what you need. Whether it's numbers, letters, punctuation, or even white space, Regex allows you to check and match any character combination in strings

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

Regexes are composed of several different components that work together to define a search pattern. The most common components include anchors, character classes, quantifiers, and alternation

### Anchors

Anchors are a different breed. They do not match any character at all. Instead, they match a position before, after, or between characters. They can be used to “anchor” the regex match at a certain position. The caret ^ matches the position before the first character in the string. Applying ^a to abc matches a. ^b does not match abc at all, because the b cannot be matched right after the start of the string, matched by ^. See below for the inside view of the regex engine.

### Quantifiers

Quantifiers are basic symbols in regular expressions that have a special meaning.
* matches previous item zero or more times
+ matches previous item once or more times
? matches previous item zero or one times; makes preceding item optional
^ matches the beginning of the string
$ matches the end of the string
. matches any single character (except line breaks)
{m, n} min is 0 or positive integer number that indicates minimum # of matches, and max is an integer equal to or greater than min indicating the maximum number of matches.

### OR Operator

For most operators that can be represented in two ways, one representation is a single character and the other is that character preceded by `\'. For example, either `(' or `\(' represents the open-group operator.

### Character Classes
Character classes are one of the most commonly used features of regular expressions. You can find a word, even if it is misspelled
With a “character class”, also called “character set”, you can tell the regex engine to match only one out of several characters. Simply place the 
characters you want to match between square brackets.
### Flags

Regular expressions may have flags that affect the search.There are only 6 of them in JavaScript:

i - With this flag the search is case-insensitive: no difference between A and a (see the example below).
g - With this flag the search looks for all matches, without it – only the first match is returned.
m - Multiline mode (covered in the chapter Multiline mode of anchors ^ $, flag "m").
s - Enables “dotall” mode, that allows a dot . to match newline character \n (covered in the chapter Character classes).
u - Enables full Unicode support. The flag enables correct processing of surrogate pairs. More about that in the chapter Unicode: flag "u" and class \p{...}.
y - “Sticky” mode: searching at the exact position in the text (covered in the chapter Sticky flag "y", searching at position

### Grouping and Capturing
# capturing (regex)
Parentheses group the regex between them. They capture the text matched by the regex inside them into a numbered group that can be reused with a numbered backreference. They allow you to apply regex operators to the entire grouped regex.
# capturing \(regex\)
Escaped parentheses group the regex between them. They capture the text matched by the regex inside them into a numbered group that can be reused with a numbered backreference. They allow you to apply regex operators to the entire grouped regex

### Bracket Expressions

Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set.

'elephant'.match(/[abcd]/) // -> matches 'a'
You can use the ^ metacharacter to negate what is between the brackets.

'donkey'.match(/[^abcd]/) // -> matches 'o'

You will often see ranges of the alphabet or all numerals. [A-Za-z] [0-9] Remember that these character sets are case sensitive, unless you set the i flag.

### Greedy and Lazy Match

You may think that <.+> (. means any non newline character and + means one or more) would only match the <em> and the </em>, when in reality it will be very greedy, and go from the first < to the last >. This means it will match <em>Hello World</em> instead of what you wanted.

Making it lazy (<.+?>) will prevent this. By adding the ? after the +, we tell it to repeat as few times as possible, so the first > it comes across, is where we want to stop the matching.

'Greedy' means match longest possible string.

'Lazy' means match shortest possible string.

For example, the greedy h.+l matches 'hell' in 'hello' but the lazy h.+?l matches 'hel'

### Boundaries

The metacharacter \b is an anchor like the caret and the dollar sign. It matches at a position that is called a “word boundary”. This match is zero-length.
There are three different positions that qualify as word boundaries:

Before the first character in the string, if the first character is a word character.

After the last character in the string, if the last character is a word character.

Between two characters in the string, where one is a word character and the other is not a word character.

Simply put: \b allows you to perform a “whole words only” search using a regular expression in the form of \bword\b. A “word character” is a character that can be used to form words. All characters that are not “word characters” are “non-word characters”.

### Back-references

Backreferences match the same text as previously matched by a capturing group. Suppose you want to match a pair of opening and closing HTML tags, and the text in between. By putting the opening tag into a backreference, we can reuse the name of the tag for the closing tag. Here’s how: <([A-Z][A-Z0-9]*)\b[^>]*>.*?</\1>. This regex contains only one pair of parentheses, which capture the string matched by [A-Z][A-Z0-9]*. This is the opening HTML tag. (Since HTML tags are case insensitive, this regex requires case insensitive matching.) The backreference \1 (backslash one) references the first capturing group. \1 matches the exact same text that was matched by the first capturing group. The / before it is a literal character. It is simply the forward slash in the closing HTML tag that we are trying to match

### Look-ahead and Look-behind

(?=foo)	Lookahead	Asserts that what immediately follows the current position in the string is foo
(?<=foo)	Lookbehind	Asserts that what immediately precedes the current position in the string is foo
(?!foo)	Negative Lookahead	Asserts that what immediately follows the current position in the string is not foo
(?<!foo)	Negative Lookbehind	Asserts that what immediately precedes the current position in the string is not foo
## Author

Adrena Lewis 
New to coding 
GitHub : https://github.com/x3n0g3n
