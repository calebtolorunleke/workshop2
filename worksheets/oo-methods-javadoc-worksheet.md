# Phase 4 Worksheet: Methods, toString(), and Javadoc

**Time**: 15 minutes | **Format**: Independent coding (on paper) | **Work with**: same partner

---

## Part A: Write Getter Methods

Add getter methods to your Student class. Follow the Person.java pattern (`public`, return type, method name, `return this.fieldName`).

```java
    /**
     * Get the ___name_______ of this student.
     *
     * @return _______"Caleb"________________________________
     */
    public ____String_____ get__StudentId_______() {
        return this.____studentId____________;
    }

    /**
     * Get the _____GPA_____ of this student.
     *
     * @return ___________the student's gpa_______________________________
     */
    public ___double______ get__Gpa_______() {
        return this.____gpa____________;
    }

    /**
     * Get the ____height______ of this student.
     *
     * @return ___________the student's height_______________________________
     */
    public ___double______ get_____height____() {
        return this.______height__________;
    }
```

---

## Part B: Write a toString() Method

The `toString()` method returns a human-readable String representation of the object. Example for Person: `"John Doe (born 1945)"`

Write a `toString()` for your Student:

```java
    /**
     * Returns a string representation of this student.
     *
     * @return a formatted string describing this student
     */
    @Override
    public String toString() {
        return ___this.name_+ " (ID: " + this.studentId + ", GPA: " + this.gpa + ")";_____;
    }
```

What does `@Override` mean?

> ---
>
> The @Override annotation informs the Java compiler that this method is intentionally replacing (overriding) a method with the exact same signature inherited from a parent class—in this case, the toString() method defined in Java's root Object class. Using @Override helps catch spelling mistakes or incorrect parameter list signatures at compile time.

---

## Part C: Peer Review Checklist

Swap your code with your partner. Check each item:

| Check | Criterion                                | Pass? |
| ----- | ---------------------------------------- | ----- |
| [ ]   | All fields are `private`                 | Yes   |
| [ ]   | Constructor is `public`                  | Yes   |
| [ ]   | All getter methods are `public`          | Yes   |
| [ ]   | Every method has a Javadoc comment       | Yes   |
| [ ]   | At least one `@param` tag is present     | Yes   |
| [ ]   | At least one `@return` tag is present    | Yes   |
| [ ]   | `this.` is used to access fields         | Yes   |
| [ ]   | `toString()` returns a String (not void) | Yes   |

One thing your partner did well:

> -Clear, descriptive Javadoc comments that explain the purpose of each parameter and return value, along with clean input validation in the constructor.--

One suggestion for improvement:

> -Add final modifiers to fields that should not change after construction (e.g., private final String studentId;) to reinforce immutability.--
