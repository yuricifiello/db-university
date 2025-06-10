# UNIVERSITY DB DATA

## table `departments`

| index | id  | name                  |
| ----- | --- | --------------------- |
| PK    | 1   | Engineering           |
| PK    | 2   | Humanities            |
| PK    | 3   | Mathematical Sciences |

---

## table `degree_courses`

| index | id  | department_id (FK) | name                   |
| ----- | --- | ------------------ | ---------------------- |
| PK    | 1   | 1                  | Electronic Engineering |
| PK    | 2   | 3                  | Computer Science       |
| PK    | 3   | 2                  | Classical Literature   |

---

## table `students`

| index | id     | degree_course_id (FK) | first_name | last_name | email                   |
| ----- | ------ | --------------------- | ---------- | --------- | ----------------------- |
| PK    | SN1001 | 2                     | Mario      | Rossi     | m.rossi@university.it   |
| PK    | SN1002 | 1                     | Laura      | Bianchi   | l.bianchi@university.it |
| PK    | SN1003 | 2                     | Giulia     | Verdi     | g.verdi@university.it   |
| PK    | SN1004 | 3                     | Marco      | Neri      | m.neri@university.it    |

---

## table `courses`

| index | id  | degree_course_id (FK) | name                  | cfu |
| ----- | --- | --------------------- | --------------------- | --- |
| PK    | 101 | 2                     | Operating Systems     | 9   |
| PK    | 102 | 1                     | Mathematical Analysis | 12  |
| PK    | 103 | 3                     | Latin Literature      | 12  |
| PK    | 104 | 2                     | Databases             | 9   |

---

## table `exam_sessions`

| index | id  | course_id (FK) | date                | classroom |
| ----- | --- | -------------- | ------------------- | --------- |
| PK    | 1   | 101            | 2025-06-20 09:00:00 | A1        |
| PK    | 2   | 102            | 2025-06-22 14:00:00 | B3        |
| PK    | 3   | 101            | 2025-07-10 09:00:00 | A1        |
| PK    | 4   | 103            | 2025-07-15 11:00:00 | C5        |
