# Palindrome Checker App

The objective of the **PalindromeChecker App** is to design and implement a console-based Java application that validates whether a given string is a palindrome under different conditions, while strengthening core programming fundamentals and data structure concepts.

---

# UC10: Case-Insensitive & Space-Ignored Palindrome

## Goal
Check whether a string is a palindrome while **ignoring spaces and letter case differences**.

---

## Flow
1. Program starts.
2. The original string is stored in a variable.
3. The string is normalized by:
    - Removing spaces.
    - Converting all characters to lowercase.
4. Characters from the start and end are compared.
5. If characters match, the comparison continues.
6. If characters differ, the string is not a palindrome.
7. The result is printed on the console.
8. Program exits.

---

## Key Concepts Used in UC10

### String Preprocessing
The string is cleaned before processing by removing spaces and converting characters to lowercase.

### Regular Expressions
Used with `replaceAll()` to remove spaces from the string.

### Data Structure
String / Array

---

## Java Implementation

```java
public class PalindromeCheckerApp {

    public static void main(String[] args) {

        String text = "Madam In Eden Im Adam";

        String normalized = text.replaceAll("\\s+", "").toLowerCase();

        boolean isPalindrome = true;
        int start = 0;
        int end = normalized.length() - 1;

        while (start < end) {

            if (normalized.charAt(start) != normalized.charAt(end)) {
                isPalindrome = false;
                break;
            }

            start++;
            end--;
        }

        if (isPalindrome) {
            System.out.println(text + " is a Palindrome (Ignoring spaces and case)");
        } else {
            System.out.println(text + " is Not a Palindrome");
        }
    }
}