# Palindrome Checker App

The objective of the **PalindromeChecker App** is to design and implement a console-based Java application that validates whether a given string is a palindrome under different conditions, while strengthening core programming fundamentals and data structure concepts.

---

# UC9: Recursive Palindrome Checker

## Goal
Check whether a string is a palindrome using **recursion**.

---

## Flow
1. Program starts.
2. The original string is stored in a variable.
3. A recursive method is called.
4. The method compares the first and last characters.
5. If characters match, the method calls itself for the next inner characters.
6. The recursion stops when the base condition is reached.
7. The result is printed on the console.
8. Program exits.

---

## Key Concepts Used in UC9

### Recursion
A technique where a method calls itself to solve smaller subproblems.

### Base Condition
Prevents infinite recursion and terminates recursive calls.

### Call Stack
A memory structure that stores method calls during recursion.

### Data Structure
Call Stack

---

## Java Implementation

```java
public class PalindromeCheckerApp {

    public static boolean isPalindrome(String text, int start, int end) {

        if (start >= end) {
            return true;
        }

        if (text.charAt(start) != text.charAt(end)) {
            return false;
        }

        return isPalindrome(text, start + 1, end - 1);
    }

    public static void main(String[] args) {

        String text = "madam";

        if (isPalindrome(text, 0, text.length() - 1)) {
            System.out.println(text + " is a Palindrome");
        } else {
            System.out.println(text + " is Not a Palindrome");
        }
    }
}