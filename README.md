# regex_learn #

## Contents ##

1. [Introduction](#Introduction)
2. [Essentials](#Essentials)
   1. [What is a Regex?](#What is a Regex?)
   2. [Literals](#Literals)
   3. 
3. [Summary](#Summary)
4. [About the Author](#About the Author)


## Introduction ##

The purpose of this tutorial is to grant the reader an overall understanding of a regular expression's (regex)
syntax. By the end of it, the reader should be able to identify a regular expression, understand its 
functionality, discern the different parts of the regular expression, and create and implement their own
regular expression.

**Note:** Henceforth, the term **"regular expression"** will be referred to by the common acronym of **"regex"** exclusively.

## Essentials ##

### What is a Regex? ###

Simply put, a regex is an expression that is used to define a **textual search pattern**. A textual search
pattern is something that can be used to search through a body of text and pick out individual parts based
on a pattern they follow.

### Literals ##

The simplest form of a textual search pattern is through use of a **literal**. Literals are exactly what they sound like.
They are when the regex used is literally a word, phrase, or other string of characters. 

For example:
```
   This is a body of text.
```
In the above example we could use a regex to search for a particular pattern in the sentence above. Such
as searching for the pattern "body" would return the word "body." For this we would use the literal string below:

```regexp
   body
```

While literals are helpful for finding specific words they aren't what makes regex such a Herculean tool. For that
we need to learn about our next topic.

### Meta Characters ###

Meta characters are what make regex so powerful. They greatly expand the versatility of the search pattern
by allowing one to not only look for specific strings of characters in a body of text but rather for generalized
patterns in the makeup of those strings.

* `\ ` The backslash is used for 
* `^`
* 

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

The first part `/^` is a

## About the Author ##

Hello my name is Devin Sinitiere. I am an aspiring software engineer. After many years of coding for fun
in my free-time I eventually decided to take the dive into making it a career by attending GA Tech's 2022
Coding Bootcamp. You can check out my GitHub page here: https://github.com/Chromodyne