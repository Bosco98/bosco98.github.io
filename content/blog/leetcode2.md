---
external: false
draft: false
title: "Solving the Reverse Words in a String in Java (Leet code problem solving Part 2 )"
description: "Leet code problem solving series"
date: 2023-01-03
---

In this series I'll be solving Leetcode problems one by one. 
## Problem
[557. Reverse Words in a String III](https://leetcode.com/problems/reverse-words-in-a-string-iii/)
	
Given a string  `s`, reverse the order of characters in each word within a sentence while still preserving whitespace and initial word order.

**Example 1:**

**Input:** s = "Let's take LeetCode contest"
**Output:** "s'teL ekat edoCteeL tsetnoc"

**Example 2:**

**Input:** s = "Mr Ding"
**Output:** "rM gniD"

## Approach
The "Reverse Words in a String III" problem is a common coding challenge that falls under the category of string manipulation. The problem statement asks us to reverse the order of characters within each word in a given sentence while maintaining the original whitespace and word order. In this article, we will explore the problem, understand the provided Java solution, and delve into a detailed explanation of the code.

**Input:**

makefileCopy code

`s = "Let's take LeetCode contest"` 

**Output:**

arduinoCopy code

`"s'teL ekat edoCteeL tsetnoc"` 

Explanation:

-   The word "Let's" becomes "s'teL".
-   The word "take" becomes "ekat".
-   The word "LeetCode" becomes "edoCteeL".
-   The word "contest" becomes "tsetnoc".
-   The order of words is maintained, and whitespace is preserved.

## Code:
Now, let's delve into the Java code that embodies this approach.

java Code : 
```
public static void main(String[] args) {  
    System.out.println(reverseWords("Let's take LeetCode contest"));  
}  
  
public static String reverseWords(String s) {  
  
    String op = "";  
    for (String a : s.split("  ")) {  
        op += reverseString(a) + " ";  
        System.out.println(op);  
    }  
    return op.substring(0, s.length());  
}  
  
public static String reverseString(String s) {  
    char[] a = s.toCharArray();  
    String op = "";  
    for (int i = a.length-1; i >= 0; i--) {  
        op += a[i];  
    }  
    return op;  
}
```
### Explanation of the Java Code:

1.  The `main` method serves as the entry point, calling the `reverseWords` method with the provided input string.
    
2.  The `reverseWords` method takes a string `s` as input and initializes an empty string `op` to store the output.
    
3.  The code uses a `for` loop to iterate over each word in the input string, which is obtained by splitting the input string using whitespace as the delimiter (`s.split(" ")`).
    
4.  For each word `a`, the code calls the `reverseString` method to reverse the characters in the word. The reversed word is then concatenated with a space to the `op` string.
    
5.  Finally, the method returns a substring of `op` from index 0 to the length of the original input string `s`. This is done to remove the extra space added after the last word.


Using string builder
```
public String reverseWords(String s) {  
    String op = "";  
    for (String a : s.split("  ")) {  
        StringBuilder sb = new StringBuilder(a);  
        sb.reverse();  
        op += sb + " ";  
    }  
    return op.substring(0,s.length());  
}
```
Javascript : 
```	
function reverseWords(s) {
    // Split the input string into words
    const words = s.split(' ');

    // Reverse each word
    const reversedWords = words.map(word => {
        return word.split('').reverse().join('');
    });

    // Join the reversed words back into a sentence
    const result = reversedWords.join(' ');

    return result;
}

// Example usage:
const input1 = "Let's take LeetCode contest";
const output1 = reverseWords(input1);
console.log(output1); // Output: "s'teL ekat edoCteeL tsetnoc"

const input2 = "Mr Ding";
const output2 = reverseWords(input2);
console.log(output2); // Output: "rM gniD"
```

Code files : [https://github.com/Bosco98/Practice/blob/main/src/RevWord.java](https://github.com/Bosco98/Practice/blob/main/src/RevWord.java)

Entire repo : [https://github.com/Bosco98/Practice/](https://github.com/Bosco98/Practice/)