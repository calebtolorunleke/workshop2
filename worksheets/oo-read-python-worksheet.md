# Phase 1 Worksheet: Function-Centric vs Object-Oriented Design

**Time**: 15 minutes | **Format**: Read the handout, then answer below | **Work with**: a partner

---

Read **both** Python designs on the Phase 1 handout. Then answer the following questions.

---

## 1. Data Representation

In Design 1 (function-centric), how is a person's data stored?

> Data are store in a standalone dictironary

In Design 2 (object-oriented), how is a person's data stored?

> ---
>
> Person's data is stored as instance variables
>
> ---

---

## 2. Calling Convention

How do you get a person's age in Design 1? Write the exact code:

> **age = getAge(john)******\_\_********

How do you get a person's age in Design 2? Write the exact code:

> **age = john.getAge()****\_******

What is the difference in who "owns" the operation?

> **In Design 1, an external top-level function own the operation and receives the data as an argument********\_\_\_**********
>
> **\_In Design 2, the john object owns the operation and acts on its own internal state**\_\_\_****

---

## 3. Where Do Functions Live?

In Design 1, where are `getAge` and `getFullName` defined? (Inside or outside the data structure?)

> **\_They are defined outside the data structure as standalone, global functions****************\_\_\_\_******************

In Design 2, where are `getAge` and `getFullName` defined?

> **\_They are defined inside the person class definition alongside the data fields******\_\_\_\_********

---

## 4. Encapsulation

Which design groups data and functions together into one unit?

> **\_Design 2 (Object-Oriented)****\_******

What is this grouping called? (Hint: it starts with "enc...")

> \_**\_Encapsulation**\_\_\_\_****

---

## 5. Adding a New Operation

Imagine you need to add a `getInitials()` function that returns "J.D." for John Doe.

In Design 1, where would you add it?

> **Anywhere in the file or module that accepts a person dictionary as a parameter**\_\_****

In Design 2, where would you add it?

> **\_Inside the Person class definition as a new method using self\_\_**

Which approach keeps related code together?

> \_\_\_Design 2 (Object-Oriented)

---

## 6. Reflection

In one sentence, what is the main advantage of object-oriented design over function-centric design?

> \__Object-oriented design bundles state and behavior into a single cohesive unit (encapsulation), making code easier to maintain, reuse, and scale as systems grow complex_
