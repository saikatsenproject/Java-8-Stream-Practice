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
```
int[] arr = {1,2,3,5,7,8};
Arrays.stream(arr)
      .filter(a -> a % 2 == 0)
      .forEach(System.out::println);
// Output: 2, 8
```
### 2. Find maximum in array
```
int max = Arrays.stream(arr)
                .max()
                .orElseThrow();
System.out.println(max);
// Output: 8
```
### 3. Sort array in descending order
```
Arrays.stream(arr)
      .boxed()
      .sorted(Collections.reverseOrder())
      .forEach(System.out::println);
// Output: 8, 7, 5, 3, 2, 1
```
### 4. Count strings with prefix "B"
```
String[] str = {"Alice","Bob","Annie","Alex","Char","Bob","Bob"};
long count = Arrays.stream(str)
                   .filter(s -> s.startsWith("B"))
                   .count();
System.out.println(count);
// Output: 3
```
### 5. Convert all strings to uppercase
```
Arrays.stream(str)
      .map(String::toUpperCase)
      .forEach(System.out::println);
// Output: ALICE, BOB, ANNIE, ALEX, CHAR, BOB, BOB
```
### 6. Check if any string contains "Bo"
```
boolean isPresent = Arrays.stream(str)
                          .anyMatch(s -> s.contains("Bo"));
System.out.println(isPresent);
// Output: true
```
### 7. Find duplicates in list
```
Set<String> set = new HashSet<>();
Set<String> duplicates = Arrays.stream(str)
                               .filter(s -> !set.add(s))
                               .collect(Collectors.toSet());
System.out.println(duplicates);
// Output: [Bob]
```
### 8. Flatten a 2D array
```
int[][] flat = {{1,2,4},{4,6,7,8}};
int[] flatArr = Arrays.stream(flat)
                      .flatMapToInt(Arrays::stream)
                      .toArray();
System.out.println(Arrays.toString(flatArr));
// Output: [1, 2, 4, 4, 6, 7, 8]
```
### 9. Find 4th largest number
```
int nthLargest = Arrays.stream(arr)
                       .boxed()
                       .sorted(Collections.reverseOrder())
                       .skip(3)
                       .findFirst()
                       .orElseThrow();
System.out.println(nthLargest);
// Output: 3
```
### 10. Reverse each string
```
List<String> reversed = Arrays.stream(str)
                              .map(s -> new StringBuilder(s).reverse().toString())
                              .collect(Collectors.toList());
System.out.println(reversed);
// Output: [ecilA, boB, einnA, xelA, rahC, boB, boB]
```
### 11. Convert map to list (keys with value > 8)
```
Map<String,Integer> map = new HashMap<>();
map.put("abc",1234);
map.put("bcd",1);
map.put("dfghj",12);
map.put("dfg",7);
map.put("sd",90);

List<String> keys = map.entrySet().stream()
                       .filter(entry -> entry.getValue() > 8)
                       .map(Map.Entry::getKey)
                       .collect(Collectors.toList());
System.out.println(keys);
// Output: [abc, dfghj, sd]
```
### 12. Partition list into even/odd
```
Map<Boolean, List<Integer>> partition = Arrays.stream(arr)
                                              .boxed()
                                              .collect(Collectors.partitioningBy(n -> n % 2 == 0));
System.out.println(partition);
// Output: {false=[1, 3, 5, 7], true=[2, 8]}
```
### 13. Most frequent characters
```
String input = "helloo";
Map<String, Long> freqMap = Arrays.stream(input.split(""))
                                  .collect(Collectors.groupingBy(c -> c, Collectors.counting()));

long maxFreq = freqMap.values().stream().max(Long::compare).orElseThrow();

List<String> mostFrequent = freqMap.entrySet().stream()
                                   .filter(entry -> entry.getValue() == maxFreq)
                                   .map(Map.Entry::getKey)
                                   .collect(Collectors.toList());

System.out.println(mostFrequent);
// Output: [o]
```
### 14. Longest word in sentence
```
String sentence = "Hi I'm practicing java8 stream API";
String longest = Arrays.stream(sentence.split(" "))
                       .max(Comparator.comparingInt(String::length))
                       .orElseThrow();
System.out.println(longest);
// Output: practicing
```
