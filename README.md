# Palindrome Checker App

The objective of the **PalindromeChecker App** is to design and implement a console-based Java application that validates whether a given string is a palindrome under different conditions, while strengthening core programming fundamentals and data structure concepts.

---

# UC8: Linked List Based Palindrome Checker

## Goal
Check whether a string is a palindrome using a **Singly Linked List**.

---

## Flow
1. Program starts.
2. The original string is stored in a variable.
3. The string is converted into a singly linked list.
4. The middle of the linked list is found using the fast and slow pointer technique.
5. The second half of the linked list is reversed.
6. The first half and reversed second half are compared.
7. If all nodes match → it is a palindrome.
8. The result is printed on the console.
9. Program exits.

---

## Key Concepts Used in UC8

### Singly Linked List
A dynamic data structure where elements are connected using node references.

### Node Traversal
Sequential access to elements using `next` references.

### Fast and Slow Pointer Technique
Used to efficiently locate the middle of the linked list.

### In-Place Reversal
Reverses the second half of the linked list without using extra memory.

### Data Structure
Singly Linked List

---

## Java Implementation

```java
public class PalindromeCheckerApp {

    static class Node {
        char data;
        Node next;

        Node(char data) {
            this.data = data;
            this.next = null;
        }
    }

    public static boolean isPalindrome(Node head) {

        if (head == null || head.next == null) {
            return true;
        }

        Node slow = head;
        Node fast = head;

        while (fast != null && fast.next != null) {
            slow = slow.next;
            fast = fast.next.next;
        }

        Node prev = null;
        Node current = slow;

        while (current != null) {
            Node next = current.next;
            current.next = prev;
            prev = current;
            current = next;
        }

        Node firstHalf = head;
        Node secondHalf = prev;

        while (secondHalf != null) {
            if (firstHalf.data != secondHalf.data) {
                return false;
            }
            firstHalf = firstHalf.next;
            secondHalf = secondHalf.next;
        }

        return true;
    }

    public static void main(String[] args) {

        String text = "madam";

        Node head = new Node(text.charAt(0));
        Node current = head;

        for (int i = 1; i < text.length(); i++) {
            current.next = new Node(text.charAt(i));
            current = current.next;
        }

        if (isPalindrome(head)) {
            System.out.println(text + " is a Palindrome");
        } else {
            System.out.println(text + " is Not a Palindrome");
        }
    }
}