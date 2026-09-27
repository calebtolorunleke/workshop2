# Workshop 02: Object-Oriented Design & Your First Java Class

**Course**: CS 5004/5010 — Object-Oriented Design
**Date**: Monday, September 21, 2026 (Week 2)
**Duration**: 2 hours
**Format**: Paper first, then IDE — bring a laptop _and_ a pen

---

## Overview

The first workshop with real content. It runs in two halves that answer two different questions:

- **On paper (first hour):** _why_ objects — what a class buys you over a bag of functions, and how
  to design one before touching a keyboard.
- **In the IDE (second hour):** _how_ — implement `DigitalClock` from scratch, with validation and
  JUnit tests, as the first project students build themselves.

Designing on paper before coding is the habit the whole term rests on. Doing both in one session is
deliberate: students see a design they made in phase 3 turn into code they run in phase 5.

> **Module 01** — _Java Fundamentals & Designing Objects_. Quiz 01 is due Sun Sep 20.
> **Assignment 01** (Track A, the animal shelter) releases at **5:00 PM today**, and its value
> objects are the same idea as the clock's constructor validation.

---

## Learning Objectives (Module 01)

By the end of this workshop, students should be able to:

- [ ] Distinguish function-centric from object-oriented design, and say what the class buys
- [ ] Read and annotate a Java class — fields, constructor, methods
- [ ] Explain `private` vs `public`, and why fields are private by default here
- [ ] Read and write Javadoc, including `@param` and `@return`
- [ ] Design a class on paper: fields, constructor, method signatures
- [ ] Implement a Java class with a private field, a validating constructor, and methods
- [ ] Enforce a class invariant by throwing `IllegalArgumentException`
- [ ] Use integer division and modulo to derive components from a stored value
- [ ] Write JUnit 5 tests, including `assertThrows`

---

## Workshop Structure

| Phase | Duration | Type           | Activity                                                      |
| ----- | -------- | -------------- | ------------------------------------------------------------- |
| 1     | 15 min   | Read (paper)   | Function-centric vs object-oriented, in Python                |
| 2     | 15 min   | Read (paper)   | Java class anatomy — `Person.java`                            |
| 3     | 20 min   | Design (paper) | Design a class of your own: fields, constructor, methods      |
| 4     | 15 min   | Design (paper) | Getters, `toString()`, Javadoc — then peer review             |
| 5     | 25 min   | Code (IDE)     | `DigitalClock`: validating constructor, getters, `toString()` |
| 6     | 20 min   | Code (IDE)     | JUnit 5 tests, including `assertThrows`                       |
| —     | 10 min   | Wrap-up        | Paper design → running code; what Assignment 01 asks          |

**The hinge is between phases 4 and 5.** Everything before it is pen and paper; everything after is
the machine. Say so explicitly when you get there.

### Pre-read, not a live phase

`handouts/python-vs-java-clock.md` puts the Python and Java DigitalClock side by side. It is
**assigned reading before the session**, not workshop time — it is syntax translation, and syntax
is better absorbed alone than in a room. Students who skip it can still follow phase 5.

### Optional / take-home

**Extend the clock** — add `getAMPM()` or `tick()`. Genuinely optional, for anyone who finishes
phase 6 early. Solutions provided.

---

## Materials Needed

### Print per student

- `Student-Workbook.md`
- Handouts: `oo-python-person.md`, `oo-java-person.md`
- Worksheets: `oo-read-python-worksheet.md`, `oo-read-java-worksheet.md`,
  `oo-design-class-worksheet.md`, `oo-methods-javadoc-worksheet.md`

### On machines

- `DigitalClockRepo/` — the Gradle project for phases 5–6.

### Instructor materials

- `Instructor-Guide.md`
- `solutions/` — every worksheet and the complete `DigitalClock`
- Whiteboard for the phase-4 peer review and the phase-3 design share

---

## Connection to Course

- **Phases 1–4 came from the old Workshop 01**, which taught this Module 01 material a week early on
  Module 00's date. See `PlanningDocuments/125-timeline-analysis.md` §F2.
- **Phase 5's validating constructor is Assignment 01 in miniature.** The shelter's `AgeMonths` and
  `Animal` do exactly this: check first, assign second, make invalid states impossible to build.
- **Phase 6's `assertThrows`** is the idiom every provided test suite in this course uses.
- Reading a class before writing one is the habit the graded **code walks** are built on.

---

## Notes

- **This workshop absorbed the old Workshop 01.** Nothing was cut except live time on the
  Python-vs-Java syntax comparison, which became pre-reading.
- **`Workshop02-Student-Packet.docx` is now stale** — it predates the merge and needs regenerating
  from `Student-Workbook.md`.

Here are the complete, precise answers to fill in your Phase 2 Worksheet based on Person.java and PersonTest.java: 2. Fields

# Type Name

1 String firstName
2 String lastName
3 int yearOfBirth
Why are all fields marked private?
To enforce encapsulation and hide internal object state. This prevents external classes from modifying the object's data directly without going through controlled public methods.

3. Constructor
   How many parameters does the constructor take? 3 (firstName, lastName, yearOfBirth)
   What does this.firstName = firstName; do? (Why is this needed here?)
   It assigns the value of the parameter firstName to the instance variable firstName. The this keyword is required to resolve variable shadowing, distinguishing the object's instance variable from the incoming method parameter of the same name.

4. Access Modifiers
   Why is the constructor marked public?
   So that outside classes (like PersonTest or a Main class) can create new instances of Person using the new keyword.

Why are the getter methods marked public?
To provide a controlled, public interface that allows external code to read the private field values.

Could another class access john.firstName directly? Why or why not?
No, because firstName is declared as private. Trying to access john.firstName directly outside the Person class will result in a compilation error.

5. Javadoc
   Find a @param tag. What does it document?
   It documents an input parameter passed into a method or constructor, detailing its name and expected description.

Find a @return tag. What does it document?
It documents the output value and data description returned by a method.

How is a Javadoc comment different from a regular // comment?
Javadoc comments start with /\*\* and are automatically extracted by tooling (like VS Code or the javadoc CLI) to generate external HTML documentation and developer hover-tooltips. Regular // comments are brief single-line notes meant only for reading raw source code.

6. JUnit Test Class
   What does @BeforeEach do?
   It executes its setup method (e.g., re-instantiating john and sally) before every single @Test method runs to guarantee a fresh, isolated state.

What does @Test mark?
It identifies a method as a runnable unit test case for the JUnit test runner.

What does assertEquals("John", this.john.getFirstName()) check?
It asserts that calling getFirstName() on this.john returns the expected String "John". If it doesn't match, the test fails.
