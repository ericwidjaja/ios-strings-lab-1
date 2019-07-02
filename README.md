# Strings Lab 1

## Instructions for lab submission

1. Fork the assignment repo
1. Clone your Fork to your machine
1. Complete the lab
1. Push your changes to your Fork
1. Submit a Pull Request back to the assignment repo
1. Paste a link to of your Fork on Canvas and submit

## Question 1

Write code that prints out all the numbers from 1 to 10 as a single string.
(Hint: the `String()` function can convert an Int to a String)
```
for i in 1...10 {
print(String(i))
}
```
***
## Question 2

Write code that prints out all the even numbers from 5 to 51 as a single string.
```
for i in 5...51 {
if i % 2 == 0 {
print(String(i))
}
}
```
***
## Question 3

Write code that prints out every number ending in 4 between 1 and 60 as a single string.
```
for i in 1...60 {
if i % 10 == 4 {
print(String(i))
}
}
```
***
## Question 4

Print each character in the string `"Hello world!"`
```
let greetings = "Hello world!"
for char in (greetings) {
print(char)
}
```
***
## Question 5

Print out the last character in the string below.  You cannot use the Character literal "!" (i.e you must access `myStringSeven`'s characters).

`let myStringSeven = "Hello world!"`
```
let myStringSeven = "Hello world!"
let lastChar = myStringSeven.last
print(lastChar ?? 0)
```
***
## Question 6

Write code that switches on a string, given the following conditions:
- If the string's length is even, print out every character.
- If the string's length is odd, print out every other character.
```var myString = "seventeen"
switch myString.count % 2 {
case 0:
for _ in myString {
print((myString),separator : " ")
}

default:
for index in 0...myString.count - 1{
if index % 2 != 0 {
let currentIndex = myString.index(myString.startIndex, offsetBy: index)
print(myString[currentIndex], terminator: " ")
}
}
}
```
***
## Question 7

Initialize a String with a character. Show that it is a Character, and not another String, that you're using to initialize it.
```
var str : String = "7"
var char = Character(str)
print(char)
```
***
## Question 8

Build five pairs of **canonically equivalent** strings, the first of each being a pre-composed character and the second being one that uses combinable unicode scalars. Show that they are equivalent.
```
let aAcutePrecomposed1 = "\u{00E1}"
print(aAcutePrecomposed1)
let aAcuteDecomposed1 = "\u{0061}\u{0301}"
print(aAcuteDecomposed1)
print(aAcutePrecomposed1 == aAcuteDecomposed1)
// prints out true because they're canonically equivalent
let aAcutePrecomposed2 = "\u{00E9}"
print(aAcutePrecomposed2)
let aAcuteDecomposed2 = "\u{0065}\u{0301}"
print(aAcuteDecomposed2)
print(aAcutePrecomposed2 == aAcuteDecomposed2)

let aAcutePrecomposed3 = "\u{00ED}"
print(aAcutePrecomposed3)
let aAcuteDecomposed3 = "\u{0069}\u{0301}"
print(aAcuteDecomposed3)
print(aAcutePrecomposed3 == aAcuteDecomposed3)

let aAcutePrecomposed4 = "\u{00F3}"
print(aAcutePrecomposed4)
let aAcuteDecomposed4 = "\u{006F}\u{0301}"
print(aAcuteDecomposed4)
print(aAcutePrecomposed4 == aAcuteDecomposed4)

let aAcutePrecomposed5 = "\u{00FA}"
print(aAcutePrecomposed5)
let aAcuteDecomposed5 = "\u{0075}\u{0301}"
print(aAcuteDecomposed5)
print(aAcutePrecomposed5 == aAcuteDecomposed5)
```
***
## Question 9

**Using only Unicode**, print out `"HELLO WORLD!"`
```
print(" \u{0048}\u{0045}\u{004C}\u{004C}\u{004F}  \u{0057}\u{004F}\u{0052}\u{004C}\u{0044}")
```
***
## Question 10

**Using only Unicode**, print out your name.
```
let myName = "  \u{0045}\u{0072}\u{0069}\u{0063} "
print(myName)
```
***
## Question 11

**Using only Unicode**, print out `"HELLO WORLD!"` in another language.
```print(" \u{0048}\u{0041}\u{004C}\u{004C}\u{004F}  \u{0057}\u{0045}\u{004C}\u{0054}\u{0021}")
```
***
## Question 12

Print the below flower box using the following information.

- The unicode number for ⚘ is U-2698
- The top and bottom of the box are represented by dashes and the rows are |
- Use the terminator argument in your print statements to print on the same line.
- Hint: It may be useful to try printing out a box of just one character to start then work your way from there.

```swift
Flower Box:
- - - - - - - - - - -
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
| ⚘ | ⚘ | ⚘ | ⚘ | ⚘ |
- - - - - - - - - - -
```
```
let fenceRow = String(repeating: "- ", count: 11)
let flowerRow = String(repeating: "| \u{2698} ", count: 5) + "| "

print(fenceRow)

for numberOfRows in 1...7 {
print(flowerRow)
}

print(fenceRow)
```
***
## Question 13

Write a program that sets up a chess board using Unicode.

```swift
Chess Board:
♖ ♘ ♗ ♕ ♔ ♗ ♘ ♖
♙ ♙ ♙ ♙ ♙ ♙ ♙ ♙




♟ ♟ ♟ ♟ ♟ ♟ ♟ ♟
♜ ♞ ♝ ♛ ♚ ♝ ♞ ♜
```
```
let blackPawn = "\u{265F} "
var blackPawnRow = String(repeating: blackPawn, count: 8)
let whitePawn = "\u{2659} "
var whitePawnRow = String(repeating: whitePawn, count: 8)

var blankRow = String(repeating: "\u{0020}", count: 8)
var blkRook = "\u{265C}\u{0020}"
var blkKnight = "\u{265E}\u{0020}"
var blkBishop = "\u{265D}\u{0020}"
var blkKing = "\u{265A}\u{0020}"
var blkQueen = "\u{265B}\u{0020}"

var whtRook = "\u{2656}\u{0020}"
var whtKnight = "\u{2658}\u{0020}"
var whtBishop = "\u{2657}\u{0020}"
var whtKing = "\u{2654}\u{0020}"
var whtQueen = "\u{2655}\u{0020}"
let blackRow = blkRook + blkKnight + blkBishop + blkKing + blkQueen + blkBishop + blkKnight + blkRook
let whiteRow = whtRook + whtKnight + whtBishop + whtQueen + whtKing + whtBishop + whtKnight + whtRook

print(whiteRow)
print(whitePawnRow)
print(String(repeating: blankRow + "\u{000A}", count: 4))
print(blackPawnRow)
print(blackRow)
```
***
## Question 14

You are given a string stored in the variable `aString`. Create new string named `replacedString` that contains the characters of the original string with all the occurrences of the character `"e"` replaced by `"\*"`.

```swift
var aString = "Replace the letter e with \*"
// Your code here
```
```
var aString = "Replace the letter e with *"
var replacedString = ""

for letter in aString {
if letter == "e" {
replacedString.append("*")
} else {
replacedString.append(letter)
}
}
print(replacedString)
```
Example:

Input:
`var aString = "Replace the letter e with *"`

Expected values:
`replacedString = "R*plac* th* l*tt*r * with *"`
***
## Question 15

You are given a string stored in variable `aString`. Create a new string called `reverse` that contains the original string in reverse order. Print the reversed string.

```swift
var aString = "this string has 29 characters"
var reverse = ""

// Your code here
```
```
var aString = "iOS 6.1 Class of 2020"
var reverse = ""
for letter in aString.reversed(){
reverse.append(letter)
}
print(reverse)
```
Example:
Input:
`var aString = "Hello"`

Output:
`"olleH"`

***
## Question 16

You are given a string stored in variable `aString`. Print `true` if `aString` is a palindrome, and `false` otherwise. A **palindrome** is a string which reads the same backward or forward.

```swift
let aString = "anutforajaroftuna"

// Your code here
```
```
var aString = "racecar"
var palindrome = ""
for letter in aString.reversed(){
palindrome.append(letter)
}
print(aString)
print(palindrome)
if aString == palindrome {
print("true")
}else {
print("false")
}
```
Example 1:
Input:
`var aString = "anutforajaroftuna"`

Output:
`true`

Example 2:
Input:
`var aString = "Hello"`

Output:
`false`

***
## Question 17

You are given a string stored in variable `problem`. Write code so that you print each word of the string on a new line.

```swift
var problem = "split this string into words and print them on separate lines"

// Your code
```
```
var problem = "split this string into words and print them on separate lines"

var wordArray = problem.components(separatedBy: " ")

for word in wordArray{ 
print(word)
}
```

Example:
Input:
`var problem ="split this string into words and print them on separate lines"`

Output:
```swift
split
this
string
into
words
and
print
them
on
separate
lines
```

***
## Question 18

You are given a string stored in variable `problem`. Write code that prints the longest word in the string.

```swift
var problem = "find the longest word in the problem description"

// Your code here
```
```
var problem = "find the longest word in the problem description"
var wordArray = problem.components(separatedBy: " ")
var longestWord = String()
for word in wordArray {
if (word.count > longestWord.count) {longestWord = word}
}
print(longestWord)

```
Example:
Input:
`var problem = "find the longest word in the problem description"`

Output:
`description`

Hint: Keep track of the longest word you encounter and also keep track of its length.

***
## Question 19

Given a string in English, create a tuple containing the number of vowels and consonants.

```swift
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"
```
```
let vowels = "aeiou"
let consonants = "bcdfghjklmnpqrstvwxyz"
let input = "Count how many vowels I have!"

var vowelsCount = 0
var consonantsCount = 0

for character in input {
if vowels.contains(character) {
vowelsCount += 1
} else if consonants.contains(character) {
consonantsCount += 1
}
}

var totalCounts = (vowels:vowelsCount,consonants:consonantsCount)

print(totalCounts)

```
***
## Question 20

Given a string of words separated by a `" "`. Write code that prints out the length of the last word.

If there is no last word print out `"No last word"`.

Example:
Input: `"How are you doing this Monday?"`

Output: `7`

***
```
var prob = "How are you doing this Monday?"
var wordArray = prob.components(separatedBy: " ")
var lastWord = String(wordArray.last ?? "no last word")
print(lastWord.count)
```
