# UNIVERSITY DB DATA

## table `teachers`

| index | id  | first_name | last_name | email                  |
| ----- | --- | ---------- | --------- | ---------------------- |
| PK    | 21  | Paolo      | Ricci     | p.ricci@university.it  |
| PK    | 22  | Anna       | Gallo     | a.gallo@university.it  |
| PK    | 23  | Luca       | Romano    | l.romano@university.it |

---

## table `course_teachers`

| index  | course_id (PK, FK) | teacher_id (PK, FK) |
| ------ | ------------------ | ------------------- |
| PK, FK | 101                | 21                  |
| PK, FK | 104                | 23                  |
| PK, FK | 104                | 21                  |

---

## table `exam_registrations`

| index | id  | student_id (FK) | exam_session_id (FK) | grade  |
| ----- | --- | --------------- | -------------------- | ------ |
| PK    | 1   | SN1001          | 1                    | 28     |
| PK    | 2   | SN1003          | 1                    | Failed |
| PK    | 3   | SN1001          | 3                    | 30     |
