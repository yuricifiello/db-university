# UNIVERSITY DB STRUCTURE

## `departments`

| Column Name | Type         | Index       | Attributes     | Description                  |
| ----------- | ------------ | ----------- | -------------- | ---------------------------- |
| **id**      | INT          | PRIMARY KEY | AUTO_INCREMENT | Unique ID for the department |
| name        | VARCHAR(255) |             | NOT NULL       | Name of the department       |

---

## `degree_courses`

| Column Name   | Type         | Index       | Attributes     | Description                     |
| ------------- | ------------ | ----------- | -------------- | ------------------------------- |
| **id**        | INT          | PRIMARY KEY | AUTO_INCREMENT | Unique ID for the degree course |
| department_id | INT          | FOREIGN KEY | NOT NULL       | Link to the `departments` table |
| name          | VARCHAR(255) |             | NOT NULL       | Name of the degree course       |

---

## `students`

| Column Name      | Type         | Index       | Attributes       | Description                        |
| ---------------- | ------------ | ----------- | ---------------- | ---------------------------------- |
| **id**           | VARCHAR(50)  | PRIMARY KEY |                  | Unique student registration number |
| degree_course_id | INT          | FOREIGN KEY | NOT NULL         | Link to the `degree_courses` table |
| first_name       | VARCHAR(100) |             | NOT NULL         | Student's first name               |
| last_name        | VARCHAR(100) |             | NOT NULL         | Student's last name                |
| email            | VARCHAR(255) |             | NOT NULL, UNIQUE | Student's institutional email      |

---

## `teachers`

| Column Name | Type         | Index       | Attributes       | Description               |
| ----------- | ------------ | ----------- | ---------------- | ------------------------- |
| **id**      | INT          | PRIMARY KEY | AUTO_INCREMENT   | Unique ID for the teacher |
| first_name  | VARCHAR(100) |             | NOT NULL         | Teacher's first name      |
| last_name   | VARCHAR(100) |             | NOT NULL         | Teacher's last name       |
| email       | VARCHAR(255) |             | NOT NULL, UNIQUE | Teacher's email           |

---

## `courses`

| Column Name      | Type         | Index       | Attributes     | Description                        |
| ---------------- | ------------ | ----------- | -------------- | ---------------------------------- |
| **id**           | INT          | PRIMARY KEY | AUTO_INCREMENT | Unique ID for the course           |
| degree_course_id | INT          | FOREIGN KEY | NOT NULL       | Link to the `degree_courses` table |
| name             | VARCHAR(255) |             | NOT NULL       | Name of the course                 |
| cfu              | INT          |             | NOT NULL       | University credits (CFU)           |

---

## `exam_sessions`

| Column Name | Type        | Index       | Attributes     | Description                    |
| ----------- | ----------- | ----------- | -------------- | ------------------------------ |
| **id**      | INT         | PRIMARY KEY | AUTO_INCREMENT | Unique ID for the exam session |
| course_id   | INT         | FOREIGN KEY | NOT NULL       | Link to the `courses` table    |
| date        | DATETIME    |             | NOT NULL       | Date and time of the exam      |
| classroom   | VARCHAR(50) |             |                | Classroom for the exam         |

---

## `course_teachers` (Linking Table)

| Column Name    | Type | Index                    | Attributes | Description                  |
| -------------- | ---- | ------------------------ | ---------- | ---------------------------- |
| **course_id**  | INT  | PRIMARY KEY, FOREIGN KEY | NOT NULL   | Link to the `courses` table  |
| **teacher_id** | INT  | PRIMARY KEY, FOREIGN KEY | NOT NULL   | Link to the `teachers` table |

---

## `exam_registrations` (Linking Table)

| Column Name     | Type        | Index       | Attributes     | Description                       |
| --------------- | ----------- | ----------- | -------------- | --------------------------------- |
| **id**          | INT         | PRIMARY KEY | AUTO_INCREMENT | Unique ID for the registration    |
| student_id      | VARCHAR(50) | FOREIGN KEY | NOT NULL       | Link to the `students` table      |
| exam_session_id | INT         | FOREIGN KEY | NOT NULL       | Link to the `exam_sessions` table |
| grade           | VARCHAR(20) |             | NOT NULL       | Grade obtained ( "28", "Failed")  |
