# Java-8-Stream-Practice
A collection of Java 8 Stream API examples with explanations, inputs, and outputs. This repository is designed as a learning resource for developers practicing functional programming in Java.

### 📑 Table of Contents
| #  | Question | Link |
|----|-----------|------|
| 1  | Print even numbers from an array | [Go to Q1](#1-print-even-numbers) |
| 2  | Find maximum in a list/array | [Go to Q2](#2-find-maximum-in-array) |
| 3  | Sort array in descending order | [Go to Q3](#3-sort-array-in-descending-order) |
| 4  | Count strings with a specific prefix | [Go to Q4](#4-count-strings-with-prefix-b) |
| 5  | Convert all strings to uppercase | [Go to Q5](#5-convert-all-strings-to-uppercase) |
| 6  | Check if any string matches a condition | [Go to Q6](#6-check-if-any-string-contains-bo) |
| 7  | Find duplicates in a list | [Go to Q7](#7-find-duplicates-in-list) |
| 8  | Flatten a 2D array into 1D | [Go to Q8](#8-flatten-a-2d-array) |
| 9  | Find the 4th largest number in an array | [Go to Q9](#9-find-4th-largest-number) |
| 10 | Reverse each string in a list | [Go to Q10](#10-reverse-each-string) |
| 11 | Convert a map to list (keys with value > 8) | [Go to Q11](#11-convert-map-to-list-keys-with-value--8) |
| 12 | Partition a list into even and odd numbers | [Go to Q12](#12-partition-list-into-evenodd) |
| 13 | Find most frequent characters in a string | [Go to Q13](#13-most-frequent-characters) |
| 14 | Find the longest word in a sentence | [Go to Q14](#14-longest-word-in-sentence) |

### 🧑‍💻 Examples
### 1. Print even numbers
int[] arr = {1,2,3,5,7,8};

Arrays.stream(arr)
      .filter(a -> a % 2 == 0)
      .forEach(System.out::println);

// Output: 2, 8
