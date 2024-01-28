---
external: false
draft: false
title: "Index of First Occurrence in a String (Leet code problem solving Part 4 )"
description: "Leet code problem solving series part 4"
date: 2024-01-06
---

In this series I'll be solving Leetcode problems for SDETs one by one. 

## Problem

[28. Find the Index of the First Occurrence in a String](https://leetcode.com/problems/find-the-index-of-the-first-occurrence-in-a-string/)

Given two strings `needle` and `haystack`, return the index of the first occurrence of `needle` in `haystack`, or `-1` if `needle` is not part of `haystack`.

**Example 1:**

**Input:** haystack = "sadbutsad", needle = "sad"
**Output:** 0
**Explanation:** "sad" occurs at index 0 and 6. The first occurrence is at index 0, so we return 0.

**Example 2:**

**Input:** haystack = "leetcode", needle = "leeto"
**Output:** -1
**Explanation:** "leeto" did not occur in "leetcode", so we return -1.

## Approach
To solve this problem, we can iterate through the `haystack` string and check if, at each index, the substring starting from that index matches the `needle` string. We create a helper function `compareString` for this purpose.

**Algorithm:**
1. If the length of `haystack` is less than the length of `needle`, return -1.
2. Iterate through the characters of `haystack`.
3. If the current character matches the first character of `needle`, call the `compareString` function to check for a match starting from that index.
4. If a match is found, return the current index.
5. If no match is found, return -1.

The `compareString` function compares each character of the substring of `haystack` starting from the given index with the characters of `needle`. If a mismatch is found, it returns false; otherwise, it returns true.

## Code:
Certainly! Let's go through the provided Java code line by line:

```java
class Solution {
    public int strStr(String haystack, String needle) {
        if (haystack.length() < needle.length()) return -1;

        for (int i = 0; i < haystack.length(); i++) {
            if (haystack.charAt(i) == needle.charAt(0)) {
                if(compareString(haystack, needle, i)) return i;
            }
        }

        return -1;
    }

    public static boolean compareString(String haystack, String needle, int idx) {
        if (haystack.length() - idx < needle.length()) return false;

        for (int i = 0; i < needle.length(); i++) {
            if (!(haystack.charAt(idx + i) == needle.charAt(i))) {
                return false;
            }
        }

        return true;
    }
}
```

### Explanation:
___

**Main Method: `strStr`**
   ```java
   public int strStr(String haystack, String needle) {
   ```
   - Declares a public method named `strStr` that takes two String parameters (`haystack` and `needle`) and returns an integer.
   - The method aims to find the index of the first occurrence of `needle` in `haystack`.

   ```java
       if (haystack.length() < needle.length()) return -1;
   ```
   - Checks if the length of `haystack` is less than the length of `needle`. If true, it means `needle` cannot be found in `haystack`, so it returns -1.

   ```java
       for (int i = 0; i < haystack.length(); i++) {
   ```
   - Initializes a loop to iterate through each character of `haystack` using the variable `i`.

   ```java
           if (haystack.charAt(i) == needle.charAt(0)) {
   ```
   - Checks if the current character in `haystack` at index `i` matches the first character of `needle`.

   ```java
               if(compareString(haystack, needle, i)) return i;
   ```
   - If there is a match, it calls the `compareString` helper method to check for the full match starting from index `i`.
   - If a match is found, it returns the current index `i`.
   ```java
       return -1;
   ```
   - If no match is found after the loop, it returns -1.

3. **Helper Method: `compareString`**
   ```java
   public static boolean compareString(String haystack, String needle, int idx) {
   ```
   - Declares a public static method named `compareString` that takes three parameters (`haystack`, `needle`, and `idx`) and returns a boolean.
   - This method compares substrings of `haystack` and `needle` starting from the given index `idx`.

   ```java
       if (haystack.length() - idx < needle.length()) return false;
   ```
   - Checks if the remaining length of `haystack` from index `idx` is less than the length of `needle`. If true, it means there cannot be a match, so it returns false.

   ```java
       for (int i = 0; i < needle.length(); i++) {
   ```
   - Initializes a loop to iterate through each character of `needle` using the variable `i`.

   ```java
           if (!(haystack.charAt(idx + i) == needle.charAt(i))) {
   ```
   - Checks if the character in `haystack` at index (`idx + i`) matches the character in `needle` at index `i`. If a mismatch is found, it returns false.

   ```java
               return false;
   ```
   - Ends the loop.

   ```java
       return true;
   ```
   - If the loop completes without finding any mismatches, it means the strings match, and it returns true.


JS code : 
```javascript
function strStr(haystack, needle) {
    if (needle.length === 0) {
        return 0; // Empty needle is always found at index 0
    }

    for (let i = 0; i <= haystack.length - needle.length; i++) {
        if (haystack.substring(i, i + needle.length) === needle) {
            return i; // Found the first occurrence, return the index
        }
    }

    return -1; // Needle not found in haystack
}

// Example usage:
console.log(strStr("sadbutsad", "sad")); // Output: 0
console.log(strStr("leetcode", "leeto")); // Output: -1
```

### Summary:

The code uses a simple approach to find the index of the first occurrence of `needle` in `haystack`. It iterates through `haystack` and checks for matches using a helper method (`compareString`). The `compareString` method ensures that the substring starting from the current index matches the `needle` string. If a match is found, the index is returned; otherwise, -1 is returned if no match is found.



Code files : [https://github.com/Bosco98/Practice/blob/main/src/palindromeAlphaNumeric.java](https://github.com/Bosco98/Practice/blob/main/src/strStrClass.java)

Entire repo : [https://github.com/Bosco98/Practice/](https://github.com/Bosco98/Practice/)

JS CODE : [https://github.com/Bosco98/Practice/tree/main/js%20code](https://github.com/Bosco98/Practice/tree/main/js%20code)