# Experiment 1: Entity-Relationship (ER) Diagram

## 🎯 Objective:
To understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application.

## 📚 Purpose:
The purpose of this workshop is to gain hands-on experience in designing ER diagrams that visually represent the structure of a database including entities, relationships, attributes, and constraints.

---

## 🧪 Choose One Scenario:

### 🔹 Scenario 1: University Database
Design a database to manage students, instructors, programs, courses, and student enrollments. Include prerequisites for courses.

**User Requirements:**
- Academic programs grouped under departments.
- Students have admission number, name, DOB, contact info.
- Instructors with staff number, contact info, etc.
- Courses have number, name, credits.
- Track course enrollments by students and enrollment date.
- Add support for prerequisites (some courses require others).

---

### 🔹 Scenario 2: Hospital Database
Design a database for patient management, appointments, medical records, and billing.

**User Requirements:**
- Patient details including contact and insurance.
- Doctors and their departments, contact info, specialization.
- Appointments with reason, time, patient-doctor link.
- Medical records with treatments, diagnosis, test results.
- Billing and payment details for each appointment.

---

## 📝 Tasks:
1. Identify entities, relationships, and attributes.
2. Draw the ER diagram using any tool (draw.io, dbdiagram.io, hand-drawn and scanned).
3. Include:
   - Cardinality & participation constraints
   - Prerequisites for University OR Billing for Hospital
4. Explain:
   - Why you chose the entities and relationships.
   - How you modeled prerequisites or billing.


## ER Diagram:

![image](https://github.com/user-attachments/assets/cb278279-0668-44a2-8adb-edd5653f26ff)


### 1. Entities and Their Attributes

Entity -	Attributes

STUDENT - STU_ID (PK), NAME, DOB, PH_NO, EMAIL

COURSE -	COURSE_ID (PK), COURSE_NAME, NO_OF_CREDITS

PROGRAM - PROGRAM_ID (PK), PROGRAM_NAME, DEPT_ID (FK)

DEPARTMENT - DEPT_ID (PK), DEPT_NAME

INSTRUCTOR - STAFF_ID (PK), STAFF_NAME, PH_NO, EMAIL, DEPT_ID (FK)

### 2. Relationships and Cardinality

Relationship - Between - Type/Cardinality - Notes

ENROLL -	STUDENT - COURSE	Many-to-Many	A student can enroll in many courses; each course can have many students

TAUGHT -	INSTRUCTOR - COURSE	One-to-Many or Many-to-Many	An instructor can teach multiple courses; a course may be taught by multiple instructors

GROUP -	PROGRAM - DEPARTMENT	Many-to-One	Multiple programs can belong to one department

### 3. Participation Constraints

STUDENT ↔ ENROLL: Partial participation (not all students need to be enrolled in courses).

COURSE ↔ ENROLL: Total participation (every course must be enrolled by at least one student).

INSTRUCTOR ↔ TAUGHT: Total participation (every course must be taught).

PROGRAM ↔ GROUP ↔ DEPARTMENT: Total on PROGRAM side, partial on DEPARTMENT side.

## RESULT:

Thus, to understand and apply the concepts of ER modeling by creating an ER diagram for a real-world application has been done successfully.


