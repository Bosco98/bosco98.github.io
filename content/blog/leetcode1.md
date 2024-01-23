---
external: false
draft: false
title: "Find the Unique Number of Occurrences (Leet code problem solving Part 1 )"
description: "Leet code problem solving series part II"
date: 2024-01-03
---

In this series I'll be solving Leetcode problems for SDETs one by one. 

## Problem
[1207. Unique Number of Occurrences](https://leetcode.com/problems/unique-number-of-occurrences/)
	
Given an array of integers  `arr`, return  `true`  _if the number of occurrences of each value in the array is  **unique**  or_ `false` _otherwise_.

**Example 1:**

**Input:** arr = [1,2,2,1,1,3]
**Output:** true
**Explanation:** The value 1 has 3 occurrences, 2 has 2 and 3 has 1. No two values have the same number of occurrences.

## Approach
To solve this problem, we'll employ a straightforward approach using a HashMap to keep track of the count of occurrences for each value in the array. Once we have the counts, we'll use a HashSet to check if the number of occurrences is unique. The idea is to compare the size of the HashMap (which represents distinct values) with the size of the HashSet (which represents unique counts). If these sizes are equal, we can confidently say that the number of occurrences for each value is unique.

**Dry Run:** To understand the algorithm, let's walk through a dry run using an example array `arr = [1, 2, 2, 1, 1, 3]`.

1.  **Initialize the HashMap:**
    
    -   Iterate through the array, updating the count for each value in the HashMap.
        
        `countMap = {1: 3, 2: 2, 3: 1}` 
        
2.  **Check for Unique Occurrences:**
    
    -   Extract the values from the HashMap and store them in a HashSet.
        
        `occurrenceSet = {3, 2, 1}` 
        
    -   Compare the sizes of the HashMap and HashSet.
        
        `Size of countMap: 3, Size of occurrenceSet: 3` 
        
    -   Since the sizes are equal, we conclude that the number of occurrences for each value is unique.


## Code:
Now, let's delve into the Java code that embodies this approach.

java Code : 

  ```import java.util.HashMap;
	import java.util.HashSet;
	import java.util.Map;
	import java.util.Set;

	public class UniqueOccurrences {

	    public static boolean uniqueOccurrences(int[] arr) {
	        Map<Integer, Integer> countMap = new HashMap<>();

	        // Count occurrences of each value in the array
	        for (int num : arr) {
	            countMap.put(num, countMap.getOrDefault(num, 0) + 1);
	        }

	        // Check if the number of occurrences is unique
	        Set<Integer> occurrenceSet = new HashSet<>(countMap.values());
	        return countMap.size() == occurrenceSet.size();
	    }

	    public static void main(String[] args) {
	        // Example usage
	        int[] arr = {1, 2, 2, 1, 1, 3};
	        System.out.println(uniqueOccurrences(arr)); // Output: true
	    }
	}
```
Javascript : 

```
	function uniqueOccurrences(arr) {
	    let countMap = new Map();

	    // Count occurrences of each value in the array
	    for (let num of arr) {
	        countMap.set(num, (countMap.get(num) || 0) + 1);
	    }

	    // Check if the number of occurrences is unique
	    let occurrenceSet = new Set(countMap.values());
	    return countMap.size === occurrenceSet.size;
	}

	// Example usage
	let arr = [1, 2, 2, 1, 1, 3];
	console.log(uniqueOccurrences(arr));
```


Code files : https://github.com/Bosco98/Practice/blob/main/src/Main.java

Entire repo : https://github.com/Bosco98/Practice/