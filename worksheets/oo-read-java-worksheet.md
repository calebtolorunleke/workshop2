# Phase 2 Worksheet: Java Class Anatomy, Access Modifiers, Javadoc & JUnit

**Time**: 20 minutes | **Format**: Annotate the handout + answer below | **Work with**: a partner

---

Read **Person.java** and **PersonTest.java** on the Phase 2 handout. Use a pen/pencil to annotate the code, then answer below.

---

## 1. Identify the Parts (annotate on the handout)

On the Person.java code:

- **Circle** all the fields (there are 3)
- **Underline** the constructor
- **Put a star** ★ next to each method
- **Draw a box** around each Javadoc comment block

---

## 2. Fields

List the three fields. For each, write the type and the name:

| #   | Type       | Name            |
| --- | ---------- | --------------- |
| 1   | **String** | **firstName**   |
| 2   | **String** | **lastName**    |
| 3   | **int**    | **yearOfBirth** |

Why are all fields marked `private`?

> ---
>
> to prevent direct access to the field from things outside the class, and provide controlled access via getters

---

## 3. Constructor

## How many parameters does the constructor take?

> 3 (firstName, lastName, yearOfBirth)

---

What does `this.firstName = firstName;` do? (Why is `this` needed here?)

> ---

> this is used to differentiate between the field and the parameter with the same name fron the incoming method. this.firstName refers to the firstName field belonging to the current Person object, while firstName refers to the constructor parameter. this is needed to distinguish the field from the parameter because they have the same name.

> This keyword is needed here because it refers to the private firstName that is being called in the class rather than the local firstName that is being called within the new method

> ---

## 4. Access Modifiers

Why is the constructor marked `public`?

> -so that other classes can create instances of Person using the new keyword--

Why are the getter methods marked `public`?

> -so other classes can access the values of the private fields in a controlled manner. To provide a controlled, public interface that allows external code to read the private field values--

Could another class access `john.firstName` directly? Why or why not?

> -No, becuase firstName is a private field. Trying to access john.firstName directly outside the person class will result in a compilation error.--

---

## 5. Javadoc

Find a `@param` tag. What does it document?

> ---
>
> It documents an input parameter passsed into a method or constructor, detailing its name and expected description

Find a `@return` tag. What does it document?

> ---
>
> It documents the output value and data description returned by a method

How is a Javadoc comment different from a regular `//` comment?

> ---
>
> Javadoc comments start with forward slash and two starts, and are authomatically extracted by tooling (like Vs Code or the javadoc CLI) to generate external HTML documentation and meant only for people reading the raw source code.

---

## 6. JUnit Test Class

Look at PersonTest.java:

What does `@BeforeEach` do?

> ---
>
> It excuses its setup method (e.g., re-instantiating john and sally) before every single @Test method runs to guarantee a fresh, isolated state.

What does `@Test` mark?

> ---
>
> It identifies a method as a runnable unit test case for the JUnit test runner.

What does `assertEquals("John", this.john.getFirstName())` check?

> ---
>
> It asserts that calling getFirstName() on this.john returns the expected String "John". If it doesn't match, the test fails.

If `yearOfBirth` is 1945, what will `getAge()` return in 2026?

> ---
>
> ## 81

---

## 7. Sketch a Class Diagram

In the box below, draw a UML class diagram for Person. Use `+` for public and `-` for private.

```
┌──────────────────────────────────────┐
│ Person                               │
├──────────────────────────────────────┤
│ - firstName: String.                 │
│ - lastName: String                   │
│ - yearOfBirth: int                   │
├──────────────────────────────────────┤
│ + getFirstName(): String             │
│ + getLastName(): String              │
│ + getYearOfBirth(): int              │
│ + getAge(): int                      │
│ + getFullName(): String              │
└──────────────────────────────────────┘
```
