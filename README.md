# Javascript exercises

This repository contains a set of exercises to practice Javascript.

1 Given a list of numbers, return the sum of the first and last numbers in the list.

<details>
<summary>code</summary>

```js
function sumFirstAndLast(numbers) {
  return numbers[0] + numbers[numbers.length - 1];
}
```

</details>
<br/>

2 Sort a list of numbers as a zigzag, this means that they must be ordered, first the largest, then the smallest, then the next largest and the next smallest, until the entire list is covered.

<details>
<summary>code</summary>

```js
function zigzag(numbers) {
  const sorted = numbers.sort((a, b) => a - b);
  const result = [];
  while (sorted.length) {
    result.push(sorted.pop());
    result.push(sorted.shift());
  }
  return result;
}
```

</details>
<br/>

3 Given a list of numbers, return the number of times that the number 7 appears in the list.

<details>
<summary>code</summary>

```js
function count7(numbers) {
  return numbers.filter((number) => number === 7).length;
}
```

</details>
<br/>

4 Given a list of numbers, return the number of times that the number 7 appears in the list, but if the number 7 appears more than 3 times, return 3.

<details>
<summary>code</summary>

```js
function count7(numbers) {
  const count = numbers.filter((number) => number === 7).length;
  return count > 3 ? 3 : count;
}
```

</details>
<br/>

5 Identify if a string is a palindrome. Thats means that the string is the same when read from left to right and from right to left.

<details>
<summary>code</summary>

```js
function isPalindrome(string) {
  return string === string.split('').reverse().join('');
}
```

</details>
<br/>

6 Calculate the factorial of a number. The factorial of a number is the product of all the numbers from 1 to the number itself.

<details>
<summary>code</summary>

```js
function factorial(number) {
  if (number === 0) return 1;
  return number * factorial(number - 1);
}
```

</details>
<br/>

7 Calculate the fibonacci of a number, that is the sum of the previous two numbers, starting with 0 and 1.

<details>
<summary>code</summary>

```js
function fibonacci(number) {
  if (number === 0) return 0;
  if (number === 1) return 1;
  return fibonacci(number - 1) + fibonacci(number - 2);
}
```

</details>
<br/>

8 Check if two strings are anagrams, that is, if they have the same letters.

<details>
<summary>code</summary>

```js
function isAnagram(string1, string2) {
  return (
    string1.split('').sort().join('') === string2.split('').sort().join('')
  );
}
```

</details>
<br/>

9 Having an array of string, return the string with the most characters.

<details>
<summary>code</summary>

```js
function longestString(strings) {
  return strings.reduce((longest, current) =>
    current.length > longest.length ? current : longest
  );
}
```

</details>
<br/>

10 Return the letter most repeated in a string and the number of times it is repeated.

<details>
<summary>code</summary>

```js
function mostRepeated(string) {
  const letters = string.split('');
  const lettersCount = letters.reduce((count, letter) => {
    count[letter] = count[letter] ? count[letter] + 1 : 1;
    return count;
  }, {});
  const mostRepeated = Object.keys(lettersCount).reduce(
    (mostRepeated, letter) =>
      lettersCount[letter] > lettersCount[mostRepeated] ? letter : mostRepeated
  );
  return [mostRepeated, lettersCount[mostRepeated]];
}
```

</details>
<br/>

11

<details>
<summary>code</summary>

```js

}
```

</details>
<br/>
