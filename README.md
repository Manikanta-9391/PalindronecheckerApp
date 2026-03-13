# Palindrome Checker App

The objective of the **PalindromeChecker App** is to design and implement a console-based Java application that validates whether a given string is a palindrome under different conditions while strengthening core programming fundamentals and data structure concepts.

---

# UC4: Character Array Based Palindrome Check

## Goal

Convert a string into a character array and check whether it is a palindrome using the two-pointer technique.

---

## Flow

1. Program starts.
2. The original string is stored in a variable.
3. The string is converted into a character array using `toCharArray()`.
4. Two pointers are created:

    * One pointer starts from the beginning of the array.
    * Another pointer starts from the end of the array.
5. Characters at both positions are compared.
6. If characters are different → it is **not a palindrome**.
7. If all characters match → it is **a palindrome**.
8. The result is printed on the console.
9. Program exits.

---

## Key Concepts Used in UC4

### Character Array (`char[]`)

A primitive array used to store individual characters of a string for index-based access.

### Array Indexing

Elements in an array are accessed using index positions starting from **0**.

### Two-Pointer Technique

One pointer starts from the beginning and the other from the end, reducing unnecessary comparisons.

### Time Complexity Awareness

This approach avoids creating extra objects and performs efficient comparisons.

### Data Structure: `char[]`

The `char[]` array is used to store characters of the string so they can be accessed and compared individually.

---

## Java Implementation

```java
public class PalindromeCheckerApp {

    public static void main(String[] args) {

        String text = "madam";

        char[] characters = text.toCharArray();

        int start = 0;
        int end = characters.length - 1;

        boolean isPalindrome = true;

        while (start < end) {

            if (characters[start] != characters[end]) {
                isPalindrome = false;
                break;
            }

            start++;
            end--;
        }

        if (isPalindrome) {
            System.out.println(text + " is a Palindrome");
        } else {
            System.out.println(text + " is Not a Palindrome");
        }
    }
}
```

---

## Sample Output

```
madam is a Palindrome
```

---

## Conclusion

This use case demonstrates how a palindrome can be checked using a **character array and the two-pointer technique**, which is more efficient because it avoids creating additional string objects and minimizes unnecessary comparisons.
