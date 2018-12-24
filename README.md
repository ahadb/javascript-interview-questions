# javascript-interview-questions
Learn basic to advanced commonly asked JavaScript interview questions from a syntactical perspective. Surprisingly over 50% of developers
struggle with these basic examples in interviews.

## Reverse a string - `beginner`
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

## Palindrome - `beginner`
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

## FizzBuzz

## Prime - `beginner`
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

## String Compression

## FizzBuzz

## Sentence Capitalization - `beginner`
Capitalize the first word on a sentence and leave the rest intact

```javascript
function capitalize(s) {
  if (typeof s !== 'string') {
    return ''
  }
  
  return s.charAt(0).toUpperCase() + s.slice(1)
}

capitalize('the quick brown fox over the lazy dog')
// => "the quick brown fox over the lazy dog"
```

## Array Chunking

## Max Characters

## Anagram

## Fibonnacci

## Find Vowels
