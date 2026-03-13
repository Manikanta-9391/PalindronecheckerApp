# Palindrome Checker App

The objective of the **PalindromeChecker App** is to design and implement a console-based Java application that validates whether a given string is a palindrome under different conditions, while strengthening core programming fundamentals and data structure concepts.

---

# UC11: Object-Oriented Palindrome Service

## Goal
Encapsulate palindrome checking logic inside a dedicated class following object-oriented programming principles.

---

## Flow
1. Program starts.
2. A `PalindromeChecker` class is created.
3. The class exposes a method `checkPalindrome()` to perform the palindrome validation.
4. The main application creates an object of the class.
5. The method is called with the input string.
6. The result is displayed on the console.
7. Program exits.

---

## Key Concepts Used in UC11

### Encapsulation
The palindrome logic is hidden inside the `PalindromeChecker` class and accessed through a public method.

### Single Responsibility Principle
The `PalindromeChecker` class is responsible only for palindrome validation.

### Data Structure
Internal structures such as arrays or character comparisons may be used within the class.

---

## Java Implementation

### PalindromeChecker Class

```java
public class PalindromeChecker {

    public boolean checkPalindrome(String text) {

        int start = 0;
        int end = text.length() - 1;

        while (start < end) {

            if (text.charAt(start) != text.charAt(end)) {
                return false;
            }

            start++;
            end--;
        }

        return true;
    }
}