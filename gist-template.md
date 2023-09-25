# Simple Regex Guide

In this guide, I will explain the basic components of Regex in a straight forward manner with no fluff.

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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

Within the scope of Regex, "^" and "$" are anchors. Anchors are used to match the starting or ending point of a line. "^" is used for the beginning while "$" is used for the end.

let str = 'JavaScript';
console.log(/t$/.test(str));

Output: True

Since JavaScript ends with a t, the $ anchor matches within the console log.

### Quantifiers

Quantifiers allow one to specify the exact number of characters need to be matched. For example, "\*" matches zero or more occurences of a given pattern whereas "+" matches one or more occurences of a given character.

let phone = "+1-(408)-555-0105";
let result = phone.match(/\d+/g);

console.log(result);

Output: ["1", "408", "555", "0105"]

In this example, the quantifier matches numbers more than one.

### OR Operator

In Regex, "|" is the or operator. Logically, an or operator is a symbol to distinguish two or more options. It could be A OR B.

const s = 'JavaScript and JS';
const pattern = /JavaScript|JS/g;
const match = s.match(pattern);

console.log(match);

Output: [ 'JavaScript', 'JS' ]

In the example, "|" provides JavaScript OR JS.

### Character Classes

Character classes allow one to define the certain set of characters needed to match a certain search pattern.

let phone = '+1-(408)-555-0105';
let re = /\d/;

console.log(phone.match(re));

Output: ["1"]

In this example, \d is used to match the first number of the string.

### Flags

Flags are used to modify the bahvoiur of regexes. For example, the g flag is used for a string to be tested against all possible matches.

const s = 'JS and js';
const re = /js/gi;

const newS = s.replace(re, 'JavaScript');
console.log(newS);

Output: JavaScript and JavaScript

In this example, g is used to replace all matches (globally).

### Grouping and Capturing

Regexes can also capture specified parts and form groups for them.

const path = 'posts/10';
const pattern = /\w+\/(\d+)/;

const match = path.match(pattern);
console.log(match);

Output: [ 'posts/10', '10', index: 0, input: 'posts/10', groups: undefined ]

In this example, the d+ demonstrates one match (one grouping).

### Bracket Expressions

Brackets define the expression to be matched.

For example, [a-z] signfies that the string can contain any lowercase letters from a to z.

### Greedy and Lazy Match

By default, regexes are greedy. They will attempt to match as many elements as possible. On the other hand, in lazy mode, regexes function in the opposite manner. They will attempt to match as few elements as possible. Hence, they return the smallest amount of matches.

### Boundaries

"/b" is a boundary which simply provides boundaries around a certain expression to return that expression.

console.log('Hello, JS!'.match(/\bJS\b/));

Output: ["JS"]

In this example, the boundaries make the expression only seek JS.

### Back-references

Back-references allow one to refer back to previously matched groups.

const message = `"JavaScript's cool". They said`;
const pattern = /([\'"]).\*?\1/;

const match = message.match(pattern);

console.log(match[0]);

Output: "JavaScript's cool"

In this example, /1 references the first capturing group.

### Look-ahead and Look-behind

Look-aheads and look-behinds allow one to check for a certain pattern before or after the main expression.

const s = '1 car is 15 feet long';
const pattern = /\d+(?=\s\*feet)/;

const match = s.match(pattern);
console.log(match);

Output: 15

In this example, "?=\s\*feet" is the lookahead which finds the 15.

## Author

Hi my name is Skyler, I am currently a student of UNB's coding bootcamp. Find my github repository at https://github.com/SkylerKeeling?tab=repositories
