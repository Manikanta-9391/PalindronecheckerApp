# Palindrome Checker App

The objective of the **PalindromeChecker App** is to design and implement a console-based Java application that validates whether a given string is a palindrome under different conditions while strengthening core programming fundamentals and data structure concepts.

---

# UC12: Strategy Pattern for Palindrome Algorithms (Advanced)

## Goal
Choose a palindrome checking algorithm dynamically using the **Strategy Design Pattern**.

---

## Flow
1. Program starts.
2. A `PalindromeStrategy` interface is defined.
3. Multiple implementations are created such as:
    - StackStrategy
    - DequeStrategy
4. The desired strategy is selected at runtime.
5. The selected strategy checks whether the string is a palindrome.
6. The result is printed on the console.
7. Program exits.

---

## Key Concepts Used in UC12

### Interface
Defines a common method `checkPalindrome()` for all palindrome algorithms.

### Polymorphism
Different classes implement the same interface but provide different behavior.

### Strategy Pattern
Allows selecting different algorithms dynamically without changing the main program.

### Data Structures
Varies depending on the strategy used (Stack, Deque, etc.).

---

## Java Implementation

### Strategy Interface

```java
public interface PalindromeStrategy {
    boolean checkPalindrome(String text);
}