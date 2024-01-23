---
external: false
draft: false
title: "Determining Palindromes (Leet code problem solving Part 3 )"
description: "Leet code problem solving series part 3"
date: 2024-01-04
---

In this series I'll be solving Leetcode problems for SDETs one by one. 

## Problem
[125. Valid Palindrome](https://leetcode.com/problems/valid-palindrome/)

A phrase is a  **palindrome**  if, after converting all uppercase letters into lowercase letters and removing all non-alphanumeric characters, it reads the same forward and backward. Alphanumeric characters include letters and numbers.

Given a string  `s`, return  `true` _if it is a  **palindrome**, or_ `false` _otherwise_.

**Example 1:**

**Input:** s = "A man, a plan, a canal: Panama"
**Output:** true
**Explanation:** "amanaplanacanalpanama" is a palindrome.

**Example 2:**

**Input:** s = "race a car"
**Output:** false
**Explanation:** "raceacar" is not a palindrome.

**Example 3:**

**Input:** s = " "
**Output:** true
**Explanation:** s is an empty string "" after removing non-alphanumeric characters.
Since an empty string reads the same forward and backward, it is a palindrome.

**Constraints:**

-   `1 <= s.length <= 2 * 105`
-   `s`  consists only of printable ASCII characters.


## Code Walkthrough:

-   The function begins by checking if the string is empty, in which case it is considered a palindrome.
-   Two pointers, `start` and `last`, are initialized to the beginning and end of the string, respectively.
-   The main loop continues until the pointers meet in the middle of the string.
-   At each step, the characters at the current positions are compared after handling non-alphanumeric characters appropriately.
-   If a mismatch is found, the function returns `false`.
-   If the loop completes, the string is deemed a palindrome.
```
class Solution {
    public boolean isPalindrome(String s) {
        if (s.isEmpty()) {
        	return true;
        }
        int start = 0;
        int last = s.length() - 1;
        while(start <= last) {
        	char currFirst = s.charAt(start);
        	char currLast = s.charAt(last);
        	if (!Character.isLetterOrDigit(currFirst )) {
        		start++;
        	} else if(!Character.isLetterOrDigit(currLast)) {
        		last--;
        	} else {
        		if (Character.toLowerCase(currFirst) != Character.toLowerCase(currLast)) {
        			return false;
        		}
        		start++;
        		last--;
        	}
        }
        return true;
    }
}
```

Using string builder
```
    public static boolean isPalindrome(String s) {
        s = s.replaceAll("[^a-zA-Z0-9]", "").toLowerCase();
        return s.contentEquals(new StringBuilder(s).reverse());
    }
```


JS code : 
```
function isPalindrome(s) {
    if (s.length === 0) {
        return true;
    }

    let start = 0;
    let last = s.length - 1;

    while (start <= last) {
        const currFirst = s.charAt(start);
        const currLast = s.charAt(last);

        if (!isLetterOrDigit(currFirst)) {
            start++;
        } else if (!isLetterOrDigit(currLast)) {
            last--;
        } else {
            if (currFirst.toLowerCase() !== currLast.toLowerCase()) {
                return false;
            }
            start++;
            last--;
        }
    }

    return true;
}

function isLetterOrDigit(char) {
    return /^[0-9a-zA-Z]$/.test(char);
}

// Test cases
const s1 = "A man, a plan, a canal: Panama";
console.log(isPalindrome(s1)); // Output: true

const s2 = "race a car";
console.log(isPalindrome(s2)); // Output: false

```

Code files : [https://github.com/Bosco98/Practice/blob/main/src/palindromeAlphaNumeric.java](https://github.com/Bosco98/Practice/blob/main/src/palindromeAlphaNumeric.java)

Entire repo : [https://github.com/Bosco98/Practice/](https://github.com/Bosco98/Practice/)

JS CODE : [https://github.com/Bosco98/Practice/tree/main/js%20code](https://github.com/Bosco98/Practice/tree/main/js%20code)