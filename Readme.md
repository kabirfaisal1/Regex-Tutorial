# Regex Tutorial

# Table-of-Contents
* [Git Repo](#git-repo)
* [User Story](#user-story)
* [Anchors](#anchors)
* [Quantifiers](#quantifiers)
* [OR Operator](#or-operator)
* [Character Classes](#character-classes)
* [Flags](#flags)
* [Grouping and Capturing](#grouping-and-capturing)
* [Bracket Expressions](#bracket-expressions)
* [Greedy and Lazy Match](#greedy-and-lazy-match)
* [Boundaries](#boundaries)
* [Escaping](#escaping)
* [Assertions](#assertions)


# [Git Repo](#table-of-contents)
```
https://github.com/kabirfaisal1/eCommerce.git

```

# [User Story](#table-of-contents)
```
AS A web development student
I WANT a tutorial explaining a specific regex
SO THAT I can understand the search pattern the regex defines

```
# [Acceptance Criteria](#table-of-contents)
```
GIVEN a regex tutorial
WHEN I open the tutorial
THEN I see a descriptive title and introductory paragraph explaining the purpose of the tutorial, a summary describing the regex featured in the tutorial, a table of contents linking to different sections that break down each component of the regex and explain what it does, and a section about the author with a link to the author’s GitHub profile
WHEN I click on the links in the table of contents
THEN I am taken to the corresponding sections of the tutorial
WHEN I read through each section of the tutorial
THEN I find a detailed explanation of what a specific component of the regex does
WHEN I reach the end of the tutorial
THEN I find a section about the author and a link to the author’s GitHub profile

```
## [Regex Components](#table-of-contents)
Regular expressions can be used to find certain patterns of characters within a string. You can also find and replace a character or sequence of characters within a string. They are also frequently used to validate input. This regex matches character information for valid e-mail addresses.

```
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions
```


###  [Anchors](#table-of-contents)
The anchors used to contain this regular expression are: ^ to start, and $ to finish.
The ^ anchor signifies a string that begins with the characters that follow it. This could be in one of two formats:

  * An exact string match, such as ^The, where the strings "The" or "The person" match, but "the" and "the person" do not. This is because a regex is case-sensitive.

  * A range of possible matches, displayed using bracket expressions. We'll discuss this in the next section.

The $ anchor signifies a string that ends with the characters that precede it. Just as with the ^ character, it can be preceded by an exact string or a range of possible matches.

So in our “Matching a Username” regex, the string must start and end with something that matches the pattern [a-z0-9_-]. You'll notice that we didn't include the pattern {3,16}, which precedes the $ character. Why? Because this is a special component called a quantifier. We'll come back to quantifiers in a moment.

###  [Quantifiers](#table-of-contents)

Quantifiers are used to communicate how many characters are expected. Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. By default, quantifiers are greedy, and will match as many characters as possible. If the ",+,?,{}" characters are found within regular expressions, they are considered quantifiers. The ? indicates the expression to match 0 or 1time. As mentioned in the summary above because there are 2 types of formats we'll use the or operator to distinguish which format we are using. In our Hex Value regular expression we have {6} (Hex Triplet Format) and {2} (Shorthand Hex Format), this indicates that the length of the component preceding these quantifiers should be 6 for {6} and 2 for {2}.

  * *—Matches the pattern zero or more times

  * +—Matches the pattern one or more times

  * ?—Matches the pattern zero or one time

  * {}—Curly brackets can provide three different ways to set limits for a match:

  * { n }—Matches the pattern exactly n number of times

  * { n, }—Matches the pattern at least n number of times

  * { n, x }—Matches the pattern from a minimum of n number of times to a maximum of x number of times
```
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Quantifiers
```

###  [Bracket Expressions](#table-of-contents)

Matches any character in the square brackets. For example [nN] [oO] matches no, nO, No, and NO. gr[ae]y matches both spellings of the word 'grey'; that is, gray and grey.

###  [OR Operator](#table-of-contents)
Remember that a bracket expression does not require the string to meet all of the requirements in the pattern. This means that ([\da-z\.-]+)|([a-z\.]{2,6}) searches for alphanumeric characters or the two special characters included in the pattern. Often, you'll want to add this same logic outside of a bracket expression, especially within a grouping construct or between two different grouping constructs.

Using the OR operator (|), the expression [abc] could be written as (a|b|c). Using our example in the grouping constructs section, we can take the original expression:
```
(abc):(xyz)
```
And then use the OR operator to convert it to the following:

```
(a|b|c):(x|y|z)
```
Now, both of the strings "abc:xyz" and "acb:xyz" would match, as well as "a:z", but "xyz:abc" would not.

###  [Character Classes](#table-of-contents)
In this regular expression, the charactor class /d is used which in Javasctipt classifies the use of any digit from 0 to 9.

###  [Flags](#table-of-contents)
Regular expressions have optional flags that allow for functionality like global searching and case-insensitive searching. These flags can be used separately or together in any order, and are included as part of the regular expression.

```
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions
```

###  [Grouping and Capturing](#table-of-contents)
There are three groups being captured in this example. Group #1 is the username of the e-mail account [a-z0-9_\.-]. The second group captures the domain name or e-mail service being used [\da-z\.-]. Lastly, the third group captures the domain extention (i.e .com or .net) [a-z\.]{2,6}


###  [Greedy and Lazy Match](#table-of-contents)
In this example we have only used greedy quantifiers + and {}, meaning that it will allow the match to expand as long as it neess to go. If these quantifiers were lazy quantifiers, they would appear as +? or {}?, this will direct the system to make the shortest match.

###  [Boundaries](#table-of-contents)
The (\d) is an anchor like the caret (^) and the dollar sign ($). It matches a position that is called a “word boundary”. The word boundary match is zero-length.

The following three positions are qualified as word boundaries:

Before the first character in a string if the first character is a word character.
After the last character in a string if the last character is a word character.
Between two characters in a string if one is a word character and the other is not.
Simply put, the word boundary \d allows you to carry the match the whole word using a regular expression in the following form:

```
\da-z\b
```

### [Escaping](#table-of-contents)
If you need to use any of the special characters literally (actually searching for a "*", for instance), you must escape it by putting a backslash in front of it. For instance, to search for "a" followed by "*" followed by "b", you'd use /a\*b/ — the backslash "escapes" the "*", making it literal instead of special.

```
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions
```

### [Assertions](#table-of-contents)
Assertions include boundaries, which indicate the beginnings and endings of lines and words, and other patterns indicating in some way that a match is possible (including look-ahead, look-behind, and conditional expressions).
```
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_Expressions/Assertions
```

