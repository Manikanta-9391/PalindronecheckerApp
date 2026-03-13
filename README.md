# Palindrome Checker App

The objective of the **PalindromeChecker App** is to design and implement a console-based Java application that validates whether a given string is a palindrome under different conditions, while strengthening core programming fundamentals and data structure concepts.

---

# UC6: Queue + Stack Based Palindrome Check

## Goal
Demonstrate the difference between FIFO and LIFO behavior using Queue and Stack to validate whether a string is a palindrome.

---

## Flow
1. Program starts.
2. The original string is stored in a variable.
3. A Queue and a Stack are created.
4. Each character of the string is:
    - Enqueued into the Queue.
    - Pushed into the Stack.
5. Characters are removed from the Queue using **dequeue**.
6. Characters are removed from the Stack using **pop**.
7. The removed characters are compared.
8. If all characters match → it is a palindrome.
9. The result is printed on the console.
10. Program exits.

---

## Key Concepts Used in UC6

### Queue
A linear data structure that follows the **First In First Out (FIFO)** principle.

### Enqueue & Dequeue Operations
Used to insert and remove elements from the queue.

### Stack vs Queue
Demonstrates the behavioral difference between **LIFO (Stack)** and **FIFO (Queue)** structures.

### Logical Comparison
Matching **dequeue output (Queue)** with **pop output (Stack)** to validate palindrome logic.

### Data Structures
- Queue
- Stack

---

## Java Implementation

```java
import java.util.Queue;
import java.util.LinkedList;
import java.util.Stack;

public class PalindromeCheckerApp {

    public static void main(String[] args) {

        String text = "madam";

        Queue<Character> queue = new LinkedList<>();
        Stack<Character> stack = new Stack<>();

        for (int i = 0; i < text.length(); i++) {
            char ch = text.charAt(i);
            queue.add(ch);
            stack.push(ch);
        }

        boolean isPalindrome = true;

        while (!queue.isEmpty()) {

            char fromQueue = queue.remove();
            char fromStack = stack.pop();

            if (fromQueue != fromStack) {
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