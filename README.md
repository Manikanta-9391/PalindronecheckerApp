# Palindrome Checker App

The objective of the **PalindromeChecker App** is to design and implement a console-based Java application that validates whether a given string is a palindrome under different conditions, while strengthening core programming fundamentals and data structure concepts.

---

# UC5: Stack-Based Palindrome Checker

## Goal
Use a stack data structure to reverse characters of a string and validate whether the string is a palindrome.

---

## Flow
1. Program starts.
2. The original string is stored in a variable.
3. A stack data structure is created.
4. Each character of the string is pushed into the stack.
5. Characters are popped from the stack to build the reversed string.
6. The reversed string is compared with the original string.
7. If both are equal → it is a palindrome.
8. The result is printed on the console.
9. Program exits.

---

## Key Concepts Used in UC5

### Stack
A linear data structure that follows the **Last In First Out (LIFO)** principle.

### Push Operation
Used to insert characters into the stack.

### Pop Operation
Used to remove characters from the stack in reverse order.

### Reversal Logic
Stack naturally reverses the order of elements, making it suitable for palindrome validation.

### Data Structure: Stack
The `Stack` class in Java is used to store characters and retrieve them in reverse order.

---

## Java Implementation

```java
import java.util.Stack;

public class PalindromeCheckerApp {

    public static void main(String[] args) {

        String text = "madam";

        Stack<Character> stack = new Stack<>();

        for (int i = 0; i < text.length(); i++) {
            stack.push(text.charAt(i));
        }

        String reversed = "";

        while (!stack.isEmpty()) {
            reversed = reversed + stack.pop();
        }

        if (text.equals(reversed)) {
            System.out.println(text + " is a Palindrome");
        } else {
            System.out.println(text + " is Not a Palindrome");
        }
    }
}