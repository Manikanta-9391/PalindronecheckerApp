## UC2: Print a Hardcoded Palindrome Result

### Objective
The objective of this use case is to check whether a predefined (hardcoded) string is a palindrome and display the result on the console.

A palindrome is a word, phrase, or sequence that reads the same forward and backward.  
Example: `madam`, `level`, `racecar`.

---

### Project Procedure
1. Create a Java class named `PalindromeCheckerApp`.
2. Write the `main()` method as the entry point of the program.
3. Declare a hardcoded string (example: `"madam"`).
4. Reverse the string using a loop.
5. Compare the original string with the reversed string.
6. Print the result using `System.out.println()`.

---

### Flow of the Project
1. Program starts.
2. A hardcoded string is stored in a variable.
3. The program reverses the string using a loop.
4. The reversed string is compared with the original string.
5. If both are equal → it is a **Palindrome**.
6. Otherwise → it is **Not a Palindrome**.
7. The result is displayed on the console.
8. Program ends.

---

### Use Case

**Actor:** User

**Flow:**
1. Program starts.
2. The system checks a hardcoded string.
3. The string is reversed internally.
4. The system compares the original and reversed strings.
5. The result (**Palindrome / Not Palindrome**) is printed on the console.
6. Program ends.

---

### Java Implementation

```java
public class PalindromeCheckerApp {

    public static void main(String[] args) {

        String original = "madam";
        String reversed = "";

        // Reverse the string
        for(int i = original.length() - 1; i >= 0; i--) {
            reversed = reversed + original.charAt(i);
        }

        // Check palindrome
        if(original.equals(reversed)) {
            System.out.println(original + " is a Palindrome");
        } else {
            System.out.println(original + " is Not a Palindrome");
        }
    }
}
```

---

### Example Output

```
madam is a Palindrome
```