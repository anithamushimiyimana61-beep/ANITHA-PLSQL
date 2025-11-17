
#  PL/SQL Collections and Records GOTO Demonstration

Anitha Mushimiyimana (ID: 27383)

##  Project Overview

This project implements a **Student Enrollment and Grading System** to practically demonstrate key concepts in advanced PL/SQL programming. It specifically showcases the effective use of **Collections**, **Records**, and **GOTO statements** within an Oracle database environment.

###  Learning Objectives

* Demonstrate proficiency with PL/SQL **Collections** (**VARRAY**, **Nested Tables**, **Associative Arrays**).
* Implement and utilize various types of **Records** (User-defined, Table-based, Records containing collections).
* Apply **GOTO statements** for structured control flow in grade assignment and error handling.
* Develop a **real-world business logic** application in the educational domain.
* Create **comprehensive testing and verification** procedures.

---

##  Project Structure

The project is organized into sequential SQL files to ensure smooth setup and execution.

```

PLSQL\_GRADING\_SYSTEM/
│
├── 01\_DATABASE\_SETUP.sql        -- Creates tables (students, courses, enrollments) and inserts sample data.
├── 02\_PACKAGE\_SPECIFICATION.sql  -- Defines all PL/SQL types (Records, Collections) and package subprograms.
├── 03\_PACKAGE\_BODY.sql           -- Contains the implementation logic for all procedures and functions.
└── 04\_MAIN\_DEMONSTRATION.sql     -- Main script to execute and showcase the package features.

````

---

##  Database Schema

| Table Name | Description | Key Fields |
| :--- | :--- | :--- |
| **`students`** | Stores student names and IDs. | `student_id` (PK) |
| **`courses`** | Stores course details and credit information. | `course_id` (PK), `credits` |
| **`enrollments`** | Links students to courses and stores numerical scores. | `enrollment_id` (PK), `score` |

**Sample Data Summary:**
* 5 Students enrolled in various courses.
* Numerical scores are stored in `enrollments` for grading demonstrations.

---

##  PL/SQL Features Demonstrated

### 1. Collections

| Collection Type | Use Case | Characteristics |
| :--- | :--- | :--- |
| **VARRAY** | **Course Roster** | Fixed size (e.g., max 20), dense, ideal for fixed class limits. |
| **Nested Table** | **All Enrollments** | Dynamically resizable, can become sparse, used for flexible system data. |
| **Associative Array** | **Student Lookup** | Indexed by `PLS_INTEGER`, fast key-based retrieval using `student_id`. |

### 2. Records

| Record Type | Use Case | Example Implementation |
| :--- | :--- | :--- |
| **User-defined** | **Grade Analysis** | Holds score, calculated letter grade, and GPA points for a single course. |
| **Table-based** | **Course Data** | Uses `%ROWTYPE` on the `courses` table for efficient database interaction. |
| **Containing Collection** | **Student Transcript** | A master record holding student details and a **Nested Table** of **Grade Analysis Records** (for all courses). |

### 3. GOTO Statements

The procedure `GRADING_SYSTEM.assign_grade_and_check` uses `GOTO` strategically:

* **Logic Routing:** Jumps to specific labels like `<<A_GRADE>>`, `<<B_GRADE>>`, or `<<F_FAIL>>` based on the input score, simplifying the grade-assignment structure.
* **Error Handling:** Jumps to a central `<<CLEANUP>>` label upon database exceptions (e.g., `NO_DATA_FOUND`) to ensure professional output and logging.

---

##  Implementation Details

The core functionality is encapsulated within the **`GRADING_SYSTEM`** package.

### Procedures and Functions

| Subprogram | Description | Concept Highlighted |
| :--- | :--- | :--- |
| `demonstrate_collections` | Displays how each of the three collection types is populated and traversed. | Collections & Iteration |
| `get_student_transcript` | Fetches a student's data and all associated grades, showcasing the complex **Record containing Collections**. | Complex Records |
| `assign_grade_and_check` | Takes an enrollment ID and score, assigning a grade using **GOTO** for flow control. | GOTO Statements |
| `calculate_course_average` | Calculates the average score for a course using a **Nested Table** to store scores. | Collection Methods |

---

---


##  Conclusion

The **Student Enrollment and Grading System** successfully meets the project requirements by applying advanced PL/SQL concepts to a unique academic scenario. The implementation is robust, demonstrating **Collection versatility**, **Record complexity**, and the structured use of **GOTO** statements.

**Status:**  **COMPLETED AND VERIFIED**

**Author:** Anitha Mushimiyimana

**Course:** Database Development with PL/SQL

**Institution:** \[AUCA]

**Date:** \[November 17, 2025]
````
