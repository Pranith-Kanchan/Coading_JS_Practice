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
