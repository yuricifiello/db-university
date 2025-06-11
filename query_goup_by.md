1. Contare quanti iscritti ci sono stati ogni anno

///
SELECT YEAR(`enrolment_date`) AS 'anno_immatricolazione', COUNT(`id`) AS 'numero_iscritti'
FROM `students`
GROUP BY YEAR(`enrolment_date`);
///

2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio

///
SELECT `office_address`, COUNT(`id`) AS 'numero_insegnanti'
FROM `teachers`
GROUP BY `office_address`
HAVING COUNT(`id`) > 1;
///

3. Calcolare la media dei voti di ogni appello d'esame

///
SELECT `exam_id`, AVG(`vote`) AS 'media_voti'
FROM `exam_student`
GROUP BY `exam_id`;
///

4. Contare quanti corsi di laurea ci sono per ogni dipartimento

///
SELECT D.`name` AS 'dipartimento', COUNT(DE.`id`) AS 'numero_corsi_laurea'
FROM `departments` AS D
JOIN `degrees` AS DE ON D.`id` = DE.`department_id`
GROUP BY D.`name`;
///
