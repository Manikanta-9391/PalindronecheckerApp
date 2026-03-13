# Palindrome Checker App

The objective of the **PalindromeChecker App** is to design and implement a console-based Java application that validates whether a given string is a palindrome under different conditions while strengthening core programming fundamentals and data structure concepts.

---

# UC13: Performance Comparison

## Goal
Compare the performance of different palindrome algorithms.

---

## Flow
1. Program starts.
2. Multiple palindrome algorithms are implemented.
3. Each algorithm is executed with the same input string.
4. Execution time is measured using `System.nanoTime()`.
5. The execution time for each algorithm is displayed.
6. Results are compared.
7. Program exits.

---

## Key Concepts Used in UC13

### System.nanoTime()
Provides a high-precision time measurement for performance analysis.

### Algorithm Comparison
Allows evaluation of which palindrome algorithm performs faster.

### Data Structures Used
- String
- Stack
- Deque

---

## Java Implementation

```java
import java.util.Stack;
import java.util.Deque;
import java.util.LinkedList;

public class PalindromePerformanceComparison {

    public static boolean checkUsingTwoPointer(String text) {
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

    public static boolean checkUsingStack(String text) {

        Stack<Character> stack = new Stack<>();

        for (char c : text.toCharArray()) {
            stack.push(c);
        }

        for (int i = 0; i < text.length(); i++) {
            if (text.charAt(i) != stack.pop()) {
                return false;
            }
        }

        return true;
    }

    public static boolean checkUsingDeque(String text) {

        Deque<Character> deque = new LinkedList<>();

        for (char c : text.toCharArray()) {
            deque.addLast(c);
        }

        while (deque.size() > 1) {
            if (deque.removeFirst() != deque.removeLast()) {
                return false;
            }
        }

        return true;
    }

    public static void main(String[] args) {

        String text = "madam";

        long startTime = System.nanoTime();
        checkUsingTwoPointer(text);
        long endTime = System.nanoTime();
        System.out.println("Two Pointer Time: " + (endTime - startTime) + " ns");

        startTime = System.nanoTime();
        checkUsingStack(text);
        endTime = System.nanoTime();
        System.out.println("Stack Time: " + (endTime - startTime) + " ns");

        startTime = System.nanoTime();
        checkUsingDeque(text);
        endTime = System.nanoTime();
        System.out.println("Deque Time: " + (endTime - startTime) + " ns");
    }
}