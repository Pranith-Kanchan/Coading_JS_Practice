
# Coading_JS_Practice

# 🚀 JavaScript Coding Questions for Practice

A collection of beginner to intermediate-level JavaScript coding problems with solutions for interview prep and learning. 🧠💻

---

## 1️⃣ Combine Two Strings Alternately
```js
const mixFun = (str1, str2) => {
    str1 = str1.toString();
    str2 = str2.toString();

    let result = '';
    let maxLength = Math.max(str1.length, str2.length);

    for (let i = 0; i < maxLength; i++) {
        if (i < str1.length) result += str1[i];
        if (i < str2.length) result += str2[i];
    }

    return result;
};

console.log(mixFun("abc", "123")); // Output: a1b2c3

```

## 2️⃣ Find the Second Largest Element in Array
```js
const findSecondLargest = (arr) => {
    if (arr.length < 2) return;

    let first = -Infinity, second = -Infinity;

    for (const num of arr) {
        if (num > first) {
            second = first;
            first = num;
        } else if (num > second && num !== first) {
            second = num;
        }
    }

    return second === -Infinity ? null : second;
};

console.log(findSecondLargest([1, 2, 3, 4, 5])); // Output: 4

```

## 3️⃣ Palindrome Check
```js
const isPalindrome = (str) => {
    const reversed = str.split('').reverse().join('');
    return str === reversed;
};

console.log(isPalindrome("racecar")); // true
console.log(isPalindrome("hello"));   // false
console.log(isPalindrome("madam"));   // true

```

## 4️⃣ Flatten a Nested Array
```js
const flattenArray = (arr) => {
    let flat = [];

    for (let i = 0; i < arr.length; i++) {
        if (Array.isArray(arr[i])) {
            flat = flat.concat(flattenArray(arr[i]));
        } else {
            flat.push(arr[i]);
        }
    }

    return flat;
};

console.log(flattenArray([1, 2, [3, 4, [5, 6]]])); // Output: [1, 2, 3, 4, 5, 6]

```

## 5️⃣ Reverse a String
```js
const reverse = (str) => {
    let res = '';
    for (let i = str.length - 1; i >= 0; i--) {
        res += str[i];
    }
    return res;
};

console.log(reverse('hello')); // Output: "olleh"

```

## 6️⃣ Find Missing Number in Sequence
```js
const FindMiss = (num) => {
    const n = num.length + 1;
    const sum = (n * (n + 1)) / 2;
    const actualSum = num.reduce((a, b) => a + b, 0);

    return sum - actualSum;
};

console.log(`Missing number: ${FindMiss([1, 2, 3, 5, 6])}`); // Output: 4

```
## 7️⃣ Word Count (Ignoring Banned Words)
```js
const findRepeatedWords = (sentence, banned) => {
    let wordsCount = {};
    let words = sentence.toLowerCase().split(' ');

    for (let word of words) {
        word = word.replace(/[^a-zA-Z0-9]/g, '');
        if (word && !banned.includes(word)) {
            wordsCount[word] = (wordsCount[word] || 0) + 1;
        }
    }

    return wordsCount;
};

const sentence = "This is a test. This test is just a test.";
const bannedWords = ["is", "a"];
console.log(findRepeatedWords(sentence, bannedWords));

```

## 8️⃣ Compare Two Arrays for Equality
```js
const findArrayEqual = (num1, num2) => {
    if (num1.length !== num2.length) return false;

    for (let i = 0; i < num1.length; i++) {
        if (num1[i] !== num2[i]) return false;
    }

    return true;
};

console.log(findArrayEqual([100, 200, 300], [100, 200, 300]) ? 'Array is Equal' : 'Array is Not Equal');

```

## 9️⃣ Find Two Numbers That Sum to Zero
```js
const findSumOfTwo = (num) => {
    let sumSet = [];
    let usedIndex = {};

    for (let i = 0; i < num.length; i++) {
        if (num[i] === 0 || usedIndex[i]) continue;

        for (let j = 0; j < num.length; j++) {
            if (num[j] === 0 || usedIndex[j]) continue;

            if (num[i] + num[j] === 0) {
                sumSet.push(num[i], num[j]);
                usedIndex[i] = true;
                usedIndex[j] = true;
            }
        }
    }

    return sumSet;
};

console.log(findSumOfTwo([1, 2, 4, -5, 3, 6, 2, 22, 5, 10, -3, 9, -1]));

```
## 🔟 Find Even and Odd Numbers
```js
const findEvOdd = (num) => {
    const even = [], odd = [];

    for (let i = 0; i < num.length; i++) {
        if (num[i] % 2 === 0) {
            even.push(num[i]);
        } else {
            odd.push(num[i]);
        }
    }

    return { even, odd };
};

const numbers = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10];
const result = findEvOdd(numbers);

console.log("Even:", result.even); // [2, 4, 6, 8, 10]
console.log("Odd:", result.odd);   // [1, 3, 5, 7, 9]

```
## 1️⃣1️⃣ Factorial of a Number
```js
const findFactorial = (num) => {
    if (num === 0 || num === 1) return 1;
    return num * findFactorial(num - 1);
};

console.log(findFactorial(5)); // Output: 120

```
## 1️⃣2️⃣ Remove Duplicates from Array
```js
const removeDuplicate = (num) => {
    let seen = {};
    let result = [];

    for (let i = 0; i < num.length; i++) {
        if (!seen[num[i]]) {
            seen[num[i]] = true;
            result.push(num[i]);
        }
    }

    return result;
};

console.log(removeDuplicate([1, 2, 3, 5, 3, 3, 2, 4, 2, 7])); // Output: [1, 2, 3, 5, 4, 7]
```
## ------------------------------------------- Custom Callback Function - Filter -----------------------
```js
const mapCustom = (arr, callback) => {
  let result = [];
  for (let i = 0; i < arr.length; i++) {
    if (callback(arr[i], i, arr)) {
      result.push(arr[i]);
    }
  }
  return result;
};

const numbers = [1, 2, 3, 4];
const result = mapCustom(numbers, num => num % 2 === 0);
console.log(result); // [2, 4]

// ------------------------------------- Reverse Words in a Sentence -----------------------------------

const reverse = (str) => {
  return str.trim().split(/\s+/).reverse().join(' ');
};

console.log(reverse('My name is pranit kanchan')); // "kanchan pranit is name My"
```
## ---------------------------------- First Letter of Each Word to Uppercase ---------------------------
```js
const firstCaps = (str) => {
  return str
    .toLowerCase()
    .split(' ')
    .map(word => word.length > 2 ? word[0].toUpperCase() + word.slice(1) : word)
    .join(' ');
};

console.log(firstCaps('pranith kanchan malpe')); // "Pranith Kanchan Malpe"
```
## ------------------------------------------- Count the Vowels -----------------------------------------
```js
const countVowels = (str) => {
  const vowels = 'aeiou';
  let count = 0;

  for (let char of str.toLowerCase()) {
    if (vowels.includes(char)) {
      console.log(char); // Optional log
      count++;
    }
  }

  return count;
};

console.log(countVowels("Hello World")); // 3
```
## ------------------------------------------- Rotate K Elements Left -----------------------------------
```js
const rotateArrayLeft = (arr, k) => {
  const n = arr.length;
  k = k % n;

  let rotated = new Array(n);
  for (let i = 0; i < n; i++) {
    let newIndex = (i - k + n) % n;
    rotated[newIndex] = arr[i];
  }

  return rotated;
};

console.log(rotateArrayLeft([1, 2, 3, 4, 5], 2)); // [3, 4, 5, 1, 2]
```
## -------------------------------------- Check if Array is Sorted ---------------------------------------
```js
const isSortedDescending = (arr) => {
  let ascending = true;
  let descending = true;

  for (let i = 1; i < arr.length; i++) {
    if (arr[i] > arr[i - 1]) ascending = false;
    if (arr[i] < arr[i - 1]) descending = false;
  }

  return ascending || descending;
};

console.log(isSortedDescending([5, 4, 3, 2])); // true
console.log(isSortedDescending([3, 4, 1]));   // false
```
##  Random Number Generator 
```js
function generateRandomNumbers(count, min, max) {
  const numbers = [];

  for (let i = 0; i < count; i++) {
    const randomNumber = Math.floor(Math.random() * (max - min + 1)) + min;
    numbers.push(randomNumber);
  }

  return numbers;
}

console.log(generateRandomNumbers(5, 10000, 99999));

```
## Fibonacci Function:
```js

const fibo = (n) => {
    let fib = [0, 1];  // Start with [0, 1], the typical Fibonacci sequence

    for (let i = 2; i < n; i++) {  // Start from the third element (index 2)
        fib.push(fib[i - 1] + fib[i - 2]);  // Add the sum of the last two elements
    }

    return fib;
};

console.log(fibo(7));  // Output: [0, 1, 1, 2, 3, 5, 8]

```
## Prime Numbers:
```js
const isPrime = (num) => {
  if (num <= 1) return false; // 0 and 1 are not prime
  for (let i = 2; i <= Math.sqrt(num); i++) {  // Only check divisors up to the square root of num
    if (num % i === 0) {
      return false;  // Found a divisor, so it's not prime
    }
  }
  return true;  // No divisors found, it's prime
};

console.log(isPrime(7));  // Output: true
console.log(isPrime(10)); // Output: false

```
## Deep Comparision of two objects
```js

function deepEqual(a, b) {
    
if(a===b) return true;

if( typeof a !=='object' || typeof b !=='object' || a ==null|| b==null){
    return false
    
}

let keyA = Object.keys(a);
let keyB = Object.keys(b);

for( let key of keyA){
    
    if(!keyB.includes(key) || !deepEqual(a[key],b[key])){
        return false
    }
}

return true

}
```
## An anagram is a word 
```js

function areAnagrams(str1, str2) {
  const normalize = str => str.replace(/\s/g, '').toLowerCase();

  const s1 = normalize(str1);
  const s2 = normalize(str2);

  if (s1.length !== s2.length) return false;

  const count = {};

  for (let char of s1) {
    count[char] = (count[char] || 0) + 1;
  }

  for (let char of s2) {
    if (!count[char]) return false;
    count[char]--;
  }

  return true;
}
```
## --------------------------------------------- Debouncing ----------------------------------------------
```js
import { View, TextInput, Text, StyleSheet } from 'react-native';
import { useEffect, useState, useRef } from 'react';

export default function App() {
  const [query, setQuery] = useState('');
  const [result, setResult] = useState('');
  const timerRef = useRef(null);

  const debounce = (fun, delay) => {
    return (...arg) => {
      if (timerRef.current) {
        clearTimeout(timerRef.current);
      }

      timerRef.current = setTimeout(() => {
        fun(...arg);
      }, delay);
    };
  };

  const handleSearch = debounce((text) => {
    setResult(`Resulted: ${text}`);
  }, 500);

  const handleChangeText = (text) => {
    setQuery(text);
    handleSearch(text); // Debounced search
  };

  return (
    <View style={styles.container}>
      <TextInput
        style={styles.input}
        value={query}
        onChangeText={handleChangeText}
        placeholder="Type something..."
      />
      <Text style={styles.result}>{result}</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    paddingTop: 100,
    paddingHorizontal: 20,
    backgroundColor: '#fff',
    flex: 1,
  },
  input: {
    borderWidth: 1,
    borderColor: '#ccc',
    padding: 10,
    fontSize: 18,
    borderRadius: 5,
  },
  result: {
    marginTop: 20,
    fontSize: 18,
    color: 'blue',
  },
});
```
