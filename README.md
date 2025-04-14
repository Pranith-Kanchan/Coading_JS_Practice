# Coading_JS_Practice

# 🚀 JavaScript Coding Questions for Practice

A collection of beginner to intermediate-level JavaScript coding problems with solutions for interview prep and learning. 🧠💻

---

## 1️⃣ Combine Two Strings Alternately
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


## 2️⃣ Find the Second Largest Element in Array
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


## 3️⃣ Palindrome Check
const isPalindrome = (str) => {
    const reversed = str.split('').reverse().join('');
    return str === reversed;
};

console.log(isPalindrome("racecar")); // true
console.log(isPalindrome("hello"));   // false
console.log(isPalindrome("madam"));   // true


## 4️⃣ Flatten a Nested Array
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


## 5️⃣ Reverse a String
const reverse = (str) => {
    let res = '';
    for (let i = str.length - 1; i >= 0; i--) {
        res += str[i];
    }
    return res;
};

console.log(reverse('hello')); // Output: "olleh"


## 6️⃣ Find Missing Number in Sequence
const FindMiss = (num) => {
    const n = num.length + 1;
    const sum = (n * (n + 1)) / 2;
    const actualSum = num.reduce((a, b) => a + b, 0);

    return sum - actualSum;
};

console.log(`Missing number: ${FindMiss([1, 2, 3, 5, 6])}`); // Output: 4


## 7️⃣ Word Count (Ignoring Banned Words)
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


## 8️⃣ Compare Two Arrays for Equality
const findArrayEqual = (num1, num2) => {
    if (num1.length !== num2.length) return false;

    for (let i = 0; i < num1.length; i++) {
        if (num1[i] !== num2[i]) return false;
    }

    return true;
};

console.log(findArrayEqual([100, 200, 300], [100, 200, 300]) ? 'Array is Equal' : 'Array is Not Equal');


## 9️⃣ Find Two Numbers That Sum to Zero
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


## 🔟 Find Even and Odd Numbers
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


## 1️⃣1️⃣ Factorial of a Number
const findFactorial = (num) => {
    if (num === 0 || num === 1) return 1;
    return num * findFactorial(num - 1);
};

console.log(findFactorial(5)); // Output: 120


## 1️⃣2️⃣ Remove Duplicates from Array
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


