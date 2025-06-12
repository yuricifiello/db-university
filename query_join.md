1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

```sql
SELECT *
FROM `students`
INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
WHERE `degrees`.`name` = 'Corso di Laurea in Economia';
```

2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

```sql
SELECT *
FROM `degrees`
WHERE `level` = 'magistrale' AND `department_id` = 7;
```

3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

```sql
SELECT *
FROM `courses`
INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
WHERE `course_teacher`.`teacher_id` = 44;
```

4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

   ```sql
   SELECT *, `degrees`.`name` AS `degree_name`, `departments`.`name` AS `department_name`
   FROM `students`
   INNER JOIN `degrees` ON `students`.`degree_id` = `degrees`.`id`
   INNER JOIN `departments` ON `degrees`.`department_id` = `departments`.`id`
   ORDER BY `students`.`surname` ASC, `students`.`name` ASC;

   ```

5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

```sql
SELECT `degrees`.`name` AS `degree_name`, `courses`.`name` AS `course_name`, `teachers`.`name` AS `teacher_name`, `teachers`.`surname` AS `teacher_surname`
FROM `degrees`
INNER JOIN `courses` ON `degrees`.`id` = `courses`.`degree_id`
INNER JOIN `course_teacher` ON `courses`.`id` = `course_teacher`.`course_id`
INNER JOIN `teachers` ON `course_teacher`.`teacher_id` = `teachers`.`id`;

```

6. Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

   ```sql
   SELECT DISTINCT `teachers`.`name`, `teachers`.`surname`
   FROM `teachers`
   INNER JOIN `course_teacher` ON `teachers`.`id` = `course_teacher`.`teacher_id`
   INNER JOIN `courses` ON `course_teacher`.`course_id` = `courses`.`id`
   INNER JOIN `degrees` ON `courses`.`degree_id` = `degrees`.`id`
   WHERE `degrees`.`department_id` = 5;

   ```
