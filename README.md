# regex_learn #

## Contents ##

1. [Introduction](#Introduction)
2. [Essentials](#Essentials)
   1. [Overview](#Overview)
   2. [Literals](#Literals)
   3. [Meta-Characters](#Meta-Characters)
3. [Summary](#Summary)
4. [About](#About)


## Introduction ##

The purpose of this tutorial is to grant the reader an overall understanding of a regular expression's (regex)
syntax. By the end of it, the reader should be able to identify a regular expression, understand its 
functionality, discern the different parts of the regular expression, and create and implement their own
regular expression.

**Note:** Henceforth, the term **"regular expression"** will be referred to by the common acronym of **"regex"** exclusively.

## Essentials ##

### Overview ###

Simply put, a regex is an expression that is used to define a **textual search pattern**. A textual search
pattern is something that can be used to search through a body of text and pick out or ignore individual parts based
on a pattern they follow.

### Literals ##

The simplest form of a textual search pattern is through use of a **literal**. Literals are exactly what they sound like.
They are when the regex used is literally a word, phrase, character, or any general string of characters.

For example:
```
   This is a body of text.
```
In the above example we could use a regex to search for a particular pattern in the sentence above. Such
as searching for the pattern "body" would return the word "body." For this we would use the literal string below:

```regexp
   (body)
```

While literals are helpful for finding specific words they aren't what makes regex such a Herculean tool. For that
we need to learn about our next topic.

### Meta-Characters ###

Meta characters are what make regex so powerful. They greatly expand the versatility of the search pattern
by allowing one to not only look for specific strings of characters in a body of text but rather for specific
patterns in the makeup of those strings.

**Note:** In order to use many special characters in your regex as literals they need to be preceded by a backslash `\`. This
is known as an escape character and denotes that you want to look for that specific symbol rather than its regex
functionality.

#### Meta Character Examples ####
* `\​` The backslash is used for both escaping special characters or literals as well as implementing various special commands.
* `^` Indicates the beginning of regex input.
* `$` Indicates the end of regex input.
* `+` Indicates that the preceding character matches the preceding character at least once.
* `\d` Indicates any digit.
* `( )` Anything enclosed in parentheses indicates a pattern you wish to match.
* `[ ]` Anything enclosed in brackets indicates a character set you wish to match.
* `{ }` Anything enclosed in curly braces indicates 

This list is far from exhaustive. You can find a more complete list here. https://www.ibm.com/docs/en/rational-clearquest/9.0.1?topic=tags-meta-characters-in-regular-expressions

## Summary ##

In order to piece everything we've learned together will be looking at the following regex and walk through
it piece by piece in order to understand what this seemingly gibberish string of characters and symbols 
actually does. 

Consider the following regex:

```regexp
   /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/
```

This regex may look like a random string at first, but it is actually a useful way to search for patterns that match
those of email addresses.

First off, `/^`, indicates that we are starting a regex.

The first major part of the regex we will examine is `([a-z0-9_\.-]+)` 

1. The first item of this portion are the parentheses `( )` which indicate that the entire contents are a pattern to match
2. Next the brackets `[ ]` contained within indicate that we are searching for a range of characters. 
3. The `a-z` can be read as `a through z` which indicates we want to match a pattern containing any of the letters of the alphabet.
4. Similarly, the `0-9` indicates we want to match any digits from 0 to 9. The 
5. `\.` indicates we want to also match a period for the separation of the username from the domain name. Notice how we prefix the `.` with a backslash `\ `. Since period is a special regex character we need to "escape" from the regex sequence to
tell it not to view the period as a command but rather as part of our match.
6. The hyphen `-` at the end is simply used as a literal that we want to look for hyphens in the string.
7. The plus `+` sign outside of the brackets indicates to require at least one or more of the preceding expression.

The following "at" `@` sign is treated as a literal. We use this because, as we should all know, email addresses separate
the username from the domain with that symbol. `e.g johndoe@gmail.com`

Now for the second big section of our regex `([\da-z\.-]+)`. Applying the principles we learned in the first part
we can analyze this one easier. 

1. Just like before the `([ ])` enclosing the matching string sets up that we are looking for a pattern matching characters.
2. The `\d` indicates that we are looking for any digit in this portion.
3. `a-z` once again indicates we are looking for any character in the alphabet.
4. `\.` sets up that we expect a period at the end of the string.
5. The hyphen serves the same purpose as in the prior pattern.

The last portion of this regex is the `{2,6}`. This simply indicates we are looking for a portion of the string here string containing
at least 2 characters and at most six. Most common email endings end with 2 or 3 characters `e.g. .co, .com, .org, etc.`; however, for 
to cover most if not all possibilities we allow up to 6.

Finally, the `$/` indicates that we are finished with our regex.

Congratulations! If you made it this far you should have a decent understanding of how regular expressions work and
are formed. This guide is far from exhaustive and there are many great materials online that explain regular expressions
in far greater detail. A quick google search


## About ##

Hello, I'm Chromodyne. I am an aspiring software engineer. After many years of coding for fun
in my free-time I eventually decided to take the dive into making it a career by attending GA Tech's 2022
Coding Bootcamp. You can check out my GitHub page here: https://github.com/Chromodyne