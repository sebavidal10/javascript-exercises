# Javascript exercises

(always wip)

This repository contains a set of exercises to practice Javascript.

1.- Given a list of numbers, return the sum of the first and last numbers in the list.

<details>
<summary>code</summary>

```js
function sumFirstAndLast(numbers) {
  return numbers[0] + numbers[numbers.length - 1];
}
```

</details>
<br/>

2.- Sort a list of numbers as a zigzag, this means that they must be ordered, first the largest, then the smallest, then the next largest and the next smallest, until the entire list is covered.

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

3.- Given a list of numbers, return the number of times that the number 7 appears in the list.

<details>
<summary>code</summary>

```js
function count7(numbers) {
  return numbers.filter((number) => number === 7).length;
}
```

</details>
<br/>

4.- Given a list of numbers, return the number of times that the number 7 appears in the list, but if the number 7 appears more than 3 times, return 3.

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

5.- Identify if a string is a palindrome. Thats means that the string is the same when read from left to right and from right to left.

<details>
<summary>code</summary>

```js
function isPalindrome(string) {
  return string === string.split('').reverse().join('');
}
```

</details>
<br/>

6.- Calculate the factorial of a number. The factorial of a number is the product of all the numbers from 1 to the number itself.

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

7.- Calculate the fibonacci of a number, that is the sum of the previous two numbers, starting with 0 and 1.

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

8.- Check if two strings are anagrams, that is, if they have the same letters.

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

9.- Having an array of string, return the string with the most characters.

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

10.- Return the letter most repeated in a string and the number of times it is repeated.

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

11.- Find the duplicates in an array of numbers.

<details>
<summary>code</summary>

```js
function findDuplicates(numbers) {
  const duplicates = [];
  const numbersCount = numbers.reduce((count, number) => {
    count[number] = count[number] ? count[number] + 1 : 1;
    return count;
  }, {});
  Object.keys(numbersCount).forEach((number) => {
    if (numbersCount[number] > 1) duplicates.push(number);
  });
  return duplicates;
}
```

</details>
<br/>

12.- Write a function to show the current day and time in a format like this: 'Today is: Monday, and current time is 2:7:15'

<details>
<summary>code</summary>

```js
function currentDayAndTime() {
  const date = new Date();
  const day = date.getDay();
  const dayName = [
    'Sunday',
    'Monday',
    'Tuesday',
    'Wednesday',
    'Thursday',
    'Friday',
    'Saturday',
  ][day];
  const hours = date.getHours();
  const minutes = date.getMinutes();
  const seconds = date.getSeconds();
  return `Today is: ${dayName}, and current time is ${hours}:${minutes}:${seconds}`;
}
```

</details>
<br/>

13.- Write a function to humanize numbers, that is, to convert a number into his ordinal representation. For example, 1 becomes 1st, 2 becomes 2nd, 3 becomes 3rd, 4 becomes 4th, and so on.

<details>
<summary>code</summary>

```js
function humanize(number) {
  const lastDigit = number % 10;
  const lastTwoDigits = number % 100;
  if (lastTwoDigits >= 11 && lastTwoDigits <= 13) return `${number}th`;
  if (lastDigit === 1) return `${number}st`;
  if (lastDigit === 2) return `${number}nd`;
  if (lastDigit === 3) return `${number}rd`;
  return `${number}th`;
}
```

</details>
<br/>

14.- Create a function to implement a binary search algorithm. A binary search or half-interval search algorithm finds the position of a specified input value within an array sorted by key value.

<details>
<summary>code</summary>

```js
function binarySearch(array, value) {
  let start = 0;
  let end = array.length - 1;
  while (start <= end) {
    const middle = Math.floor((start + end) / 2);
    if (array[middle] === value) return middle;
    if (array[middle] < value) start = middle + 1;
    else end = middle - 1;
  }
  return -1;
}
```

</details>
<br/>

15.- Function to detect if a number is prime.

<details>
<summary>code</summary>

```js
function isPrime(number) {
  if (number < 2) return false;
  if (number === 2) return true;
  if (number % 2 === 0) return false;
  for (let i = 3; i <= Math.sqrt(number); i += 2) {
    if (number % i === 0) return false;
  }
  return true;
}
```

</details>
<br/>

16.- Look this example, and then implement the function to return the same result.

```js
> take([1,2,3], 1)
[2, 3]
> take([1,2,3], 2)
[3]
> take([1,2,3])
[2, 3]
```

<details>
<summary>code</summary>

```js
function take(array, n = 1) {
  return array.slice(n);
}
```

</details>
<br/>

17.- Connect to poke-api (https://pokeapi.co/api/v2/pokemon?limit=100) and get the name of first 100 pokemons

<details>
<summary>code</summary>

```js
// connect to pokeapi and get the pokemons name only using vanilla js and fetch
fetch('https://pokeapi.co/api/v2/pokemon?limit=100')
  .then((response) => response.json())
  .then((data) => {
    const pokemons = data.results.map((pokemon) => pokemon.name);
    console.log(pokemons);
  });
```

</details>

18.- Connect to Rick and Morty API (https://rickandmortyapi.com/api/character) and get url image of 'Beth Smith'

<details>
<summary>code</summary>

```js
// connect to Rick and Morty API and get url for 'Beth Smith'
fetch('https://rickandmortyapi.com/api/character')
  .then((response) => response.json())
  .then((data) => {
    const beth = data.results.find(
      (character) => character.name === 'Beth Smith'
    );
    console.log(beth.image);
  });
```

</details>

19.- Sort array list of name bye length

<details>
<summary>code</summary>

```js
const names = ['John', 'Harrison Ford', 'George', 'Jai', 'Peterson'];
names.sort((a, b) => a.length - b.length);
console.log(names);
```
