# UC3 - Palindrome Check Using String Reverse

## Goal
Check whether a string is a palindrome by reversing it and comparing it with the original string.

---

## Flow
1. Program starts.
2. The original string is stored in a variable.
3. The program reverses the string using a loop.
4. The reversed string is compared with the original string.
5. If both strings are equal → it is a palindrome.
6. The result is displayed on the console.
7. Program exits.

---

## Key Concepts Used in UC3

### 1. Loop (for loop)
Used to iterate through the characters of the string in reverse order.

### 2. String Immutability
In Java, `String` objects are immutable. This means once a string is created, its value cannot be changed. Any modification creates a new `String` object.

### 3. String Concatenation (+)
Used to build the reversed string character by character.

### 4. equals() Method
Used to compare the actual content of two `String` objects rather than their memory references.

### 5. Data Structure: String
A `String` is a sequence of characters used to store and manipulate text.

---

## Java Implementation

```java
public class PalindromeCheckerApp {

    public static void main(String[] args) {

        String original = "madam";
        String reversed = "";

        for (int i = original.length() - 1; i >= 0; i--) {
            reversed = reversed + original.charAt(i);
        }

        if (original.equals(reversed)) {
            System.out.println(original + " is a Palindrome");
        } else {
            System.out.println(original + " is Not a Palindrome");
        }
    }
}