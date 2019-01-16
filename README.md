# javascript-interview-questions
Learn basic to advanced commonly asked JavaScript interview questions from a syntactical perspective. Surprisingly over 50% of developers
struggle with these basic examples in interviews.

`B` - Beginner, `I` - Intermediate, `A` - Advanced

## `B` Reverse a string
Reverse a string with a function:

```javascript
function reverseStr(str) {
  var splitStr = str.split('')
  var reverseArr = splitStr.reverse()
  var joinReversedArr = reverseArr.join('')
  
  return joinReversedArr
}

reverseStr('How are you doing?')
// => "?gniod uoy era woH"
```

Reverse a string with built in methods

```javascript
var str = 'This is a normal sized string'
var reversedStr = str.split('').reverse().join('')
reversedStr
// => "?gniod uoy era woH"
```

## `B` Palindrome
Check for a palindrome

```javascript
function palindrome(str) {
  return str === str.split('').reverse().join('')
}

palindrome('civic')
// => true
```

Build a better function that checks for palindrome using regex

```javascript
function palindrome(str) {
  var re = /[\W_]/g
  var lowRegSgtr = str.toLowerCase().replace(re, '')
  var reverseStr = lowRegSgtr.split('').reverse().join('')
  
  return reverseStr === lowRegSgtr
}

palindrome('A man, a plan, a canal. Panama')
// => true
```

## `B` FizzBuzz
Solve the fizzbuzz challenge

```javascript
function fizzBuzz() {
  for (var i = 1; i < 100; i++) {
    if (i % 15 === 0) {
      console.log('FizzBuzz')
    } else if (i % 3 === 0) {
      console.log('Fizz')
    } else if (i % 5 === 0) {
      console.log('Buzz')
    } else {
      console.log(i)
    }
  }
}
```

Using a generator

```javascript
function *fizzBuzz() {
  var i = 0
  while (true) {
    ++i
    if (i % 3 === 0 && i % 5 === 0) {
      yield 'Fizz Buzz'
    } else if (i % 3 === 0) {
      yield 'Fizz'
    } else if (i % 5 === 0) {
      yield 'Buzz'
    } else {
      yield i
    }
  }
}

var fizzBuzzGen = fizzBuzz()
fizzBuzzGen.next()

// or
for (var i = 1; i < 100; i++) {
  fizzBuzzGen.next().value + ' '
}
```

## `B` Prime
Find prime numbers in an array of n numbers

```javascript
function isPrime(val) {
  for (var i = 2; i < value; i++) {
    if (value % i === 0) {
      return false
    }
  }
  return value > 1
}

isPrime(11)
// => true

isPrime(9)
// => false

isPrime(3)
// => true

isPrime(4)
// => false
```

## `A` String Compression

## `B` Sentence Capitalization
Capitalize the first word on a sentence and leave the rest intact
```javascript
function capitalize(str) {
  var words = []

  for (let word of str.split(' ')) {
    words.push(word[0].toUpperCase() + word.slice(1))
  }

  return words.join(' ')
}
```

> an even simpler technique
```javascript
function capitalize(str) {
  if (typeof str !== 'string') {
    return ''
  }
  
  return str.charAt(0).toUpperCase() + str.slice(1)
}

capitalize('the quick brown fox over the lazy dog')
// => "The quick brown fox over the lazy dog"
```

## `I` Array Chunking
Create a chunked array (with sub arrays) given an array and chunk size
```javascript
function chunk(arr, size) {
  var chunkedArr = []

  for (let el of arr) {
    var last = chunkedArr[chunkedArr.length - 1]
    
    if (!last || last.length === size) {
        chunkedArr.push([el])
    } else {
        last.push(el)
    }
  }

  return chunkedArr
}

chunk([1, 2, 3], 2)
// =>  [[1, 2], 3]
```

## `I` Max Characters
Given a string, return the character that is most commonly used in the string

```javascript
function maxChar(str) {
  const characterMap = {}
  let max = 0
  let maxCharacter = ''

  for (let char of str) {
    if (!characterMap[char]) {
      characterMap[char] = 1
    } else {
      characterMap[char] = characterMap[char] + 1
    }
  }

  for (let char in characterMap) {
    if (characterMap[char] > 0) {
      max = characterMap[char]
      maxChar = char
    }
  }

  return maxChar    
}    
```

## Anagram

## Fibonnacci

## `B` Find All Vowels in a String
Determine the count of all vowels in a particular string. The simplest version below

```javascript
function vowels(str) {
  var matches = str.match(/[aeiou]/gi)
  return matches ? matches.length : 0
}

vowels('aeiou')
// => 5
```

## `I` Random String 
Create a function that prints out a random string with both numbers and letters with a user specified length
as a parameter

```javascript
function rand(strLen) {
  strLen = typeof(strLen === 'number' &&  strLen > 0 ? strLen : false)
  
  if (strLen) {
    var possibleCharacters = 'abcdefghijklmnopqrstuvwxyz0123456789'
      var str = ''
      
      for (i = 1; i < strLen; i++) {
        var randomCharacter = possibleCharacters.charAt(Math.floor(Math.random() * possibleCharacters.length))
        str += randomCharacter
      }
      return str
  } else {
    return false
  }
}
```

## `I` Given an Array of Integers, Return the Smallest Positive Integer Not In It

```javascript
function findNumber(values) {
  let result = [];

  for (let i = 0; i < values.length; ++i) {
    if (0 <= values[i]) {
      result[values[i]] = true;
    }
  }

  for (let i = 1; i <= result.length; ++i) {
    if (undefined === result[i]) {
      return i;
    }
  }

  return 1
}

findNumber([1, 2, 3, 5, 6, 7, 8, 9])
//=> 4
```

## `A` What will the code below output to the console and why?
```javascript
var baz = {
  foo: "bar",
  func: function() {
    var self = this
    console.log("my outer func:  this.foo = " + this.foo)
    console.log("my outer func:  self.foo = " + self.foo)
      (function() {
        console.log("my inner func:  this.foo = " + this.foo)
        console.log("my inner func:  self.foo = " + self.foo)
      }())
  }
}

baz.func()

/* $ =>
my outer func:  this.foo = bar
my outer func:  self.foo = bar
my inner func:  this.foo = undefined
my inner func:  self.foo = bar
*/
```
