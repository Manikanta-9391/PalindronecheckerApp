# Palindrome Checker App

The objective of the **PalindromeChecker App** is to design and implement a console-based Java application that validates whether a given string is a palindrome under different conditions, while strengthening core programming fundamentals and data structure concepts.

---

# UC7: Deque-Based Optimized Palindrome Checker

## Goal
Use a **Deque (Double Ended Queue)** to directly compare the first and last characters of a string to determine whether it is a palindrome.

---

## Flow
1. Program starts.
2. The original string is stored in a variable.
3. A Deque data structure is created.
4. Characters of the string are inserted into the deque.
5. The first and last characters are removed.
6. The removed characters are compared.
7. If characters match, the process continues.
8. If characters differ, the string is not a palindrome.
9. The result is printed on the console.
10. Program exits.

---

## Key Concepts Used in UC7

### Deque (Double Ended Queue)
A data structure that allows insertion and deletion from both the **front and rear** ends.

### Front and Rear Access
Deque allows direct comparison of **first and last characters**.

### Optimized Data Handling
This method eliminates the need for extra reversal structures like stacks.

### Data Structure
Deque

---

## Java Implementation

```java
import java.util.Deque;
import java.util.LinkedList;

public class PalindromeCheckerApp {

    public static void main(String[] args) {

        String text = "madam";

        Deque<Character> deque = new LinkedList<>();

        for (int i = 0; i < text.length(); i++) {
            deque.addLast(text.charAt(i));
        }

        boolean isPalindrome = true;

        while (deque.size() > 1) {

            char first = deque.removeFirst();
            char last = deque.removeLast();

            if (first != last) {
                isPalindrome = false;
                break;
            }
        }

        if (isPalindrome) {
            System.out.println(text + " is a Palindrome");
        } else {
            System.out.println(text + " is Not a Palindrome");
        }
    }
}