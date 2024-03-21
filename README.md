#### Create table

```sql
create Table student(
    id INT,
    name VARCHAR(50),
    birth_date DATE,
    phone VARCHAR(12),
    gender VARCHAR(1) );
```

### Insert Data in Tables

```sql
INSERT INTO student (
        id,
        name,
        phone,
        birth_date,
        gender
    )
    VALUES(
        1,
        "Manik",
        "015478656",
        "1930-07-15",
        "F"
    );
```

### Insert Multiple Rows

```sql
INSERT INTO student (id, name, phone, birth_date, gender)
VALUES
(1, "Jony", "04576530", "2001-09-10", "F"),
(2, "Kamal", "04576531", "2003-02-15", "F"),
(3, "Rasel", "04576528", "2001-11-17", "M"),
(4, "John", "04576529", "2002-05-20", "M"),
(5, "Alice", "04576530", "2001-09-10", "F"),
(6, "Emma", "04576531", "2003-02-15", "F"),
(7, "Michael", "04576532", "2000-12-28", "M"),
(8, "Sophia", "04576533", "2002-10-05", "F"),
(9, "David", "04576534", "2001-07-03", "M"),
(10, "Olivia", "04576535", "2000-04-19", "F"),
(11, "James", "04576536", "2003-08-22", "M");
```

### List Of Constraints In MySQL

    -NOT NULL
    -UNIQUE
    -DEFAULT
    -CHECK
    -FORELGN KEY
    -PRIMAEY KEY

```sql
    CREATE TABLE student(
        id INT NOT NULL UNIQUE,
        name VARCHAR(50) NOT NULL,
        age INT NOT NULL CHECK(age>=18),
        gender VARCHAR(10) NOT NULL,
        phone VARCHAR(10) NOT NULL UNIWQUE,
        city VARCHAR(10) NOT NULL DEFFAULT 'MIRPUR',
    );

```

### show data from Tables with SQL

    SELECT column1, column2, column3
    FROM table_name;

### shwo data all

    SELECT * FROM table_name;

### chang Name Title Bar

    SELECT id AS ID, name AS "Full Name", age AS Age
    FROM table_name;

### WHERE Comoparison Operator

1. = Equal
2. > Geater Than
3. < Less Than
4. > = Lreate than or Equal
5. <= Less than or Equal
6. <> or != NOT equal
7. BETWEEN Between a cerain range
8. LIKE Search for a pattern
9. IN To specify multiple possible values for a column

### SELECT With WHERE Clause

        SELECT column1, column2, column3
        FROM table_name

### Less than or Equal

```sql

SELECT *
From personal
where age <=20;

```

### NOT equal

```sql
    SELECT * FROM student
    where gender !="F"
```

### show name and Id

```sql
SELECT name, br_date FROM student
where gender !="F";
```

### AND OR NOR

### AND

##### all condison true show ans

```sql
SELECT * FROM personal
where age=29 and city ="MIRPUR";
```

### OR

##### one and more condison treu shwo ans

```sql
SELECT * FROM personal
where age=19 OR city ="MIRPUR";
```

```sql
SELECT * FROM personal
where (age=19 OR city ="MIRPUR") and name = "Mahodi";
```

### NOT

```sql
SELECT * FROM personal
where not (age=19 OR city ="MIRPUR");
```

### IN OPERATOR

```sql
SELECT * FROM personal
where age In(29,21)
```

### NOT IN

```sql
SELECT * FROM personal
where age NOT In(29,21)
```

### BETWEEN OPERATOR

```sql
SELECT * FROM personal
where age BETWEEN(29 and 21)
```

```sql
SELECT * FROM personal
where age BETWEEN 1998-01-01 AND 1998-06-30
```

```sql
SELECT * FROM personal
where age NOT BETWEEN 1998-01-01 AND 1998-06-30
```

### LIKE OPERATOR

###### % Percentage Sing: Repesent Zero, one or Multiple Chareacters

```sql
SELECT * FROM personal
where name like "s%";
```

Start with "a"

```sql
SELECT * FROM personal
where name like "%s";
```

End with "a"

```sql
SELECT * FROM personal
where name like "%sa%";
```

Have "sa" in any Position

```sql
SELECT * FROM personal
where name like "s%a";
```

start with "a" and Ends with "m"

```sql
SELECT * FROM personal
where name like "_a%";
```

"a"in the Second Position

```sql
SELECT * FROM personal
where name like "__a%";
```

"a"in the third Position

```sql
SELECT * FROM personal
where name like "__oy";
```

"o" in the second and "y" in the third Position

```sql
SELECT * FROM personal
where BINARY name like "__oy";
```

case in sensetive

### Regular Expression

```
^ => Beginning of string
$ => End of string
[...]=> Any chareter listed between the square brackets
^[..]=> Begins with any charachter listed between the square brackers
[a-z]=> Match With in the range
p1|p2|p3 => Matches any of the patterns p1,p2,p3
```

### Regular Expression

```sql
SELECT * FROM personal
where name regexp "ru"
```

```sql
SELECT * FROM personal
where name regexp "^a"
```

```sql
SELECT * FROM personal
where name regexp "k$"
```

```sql
SELECT * FROM personal
where name regexp "k$"
```

```sql
SELECT * FROM personal
where name regexp "mahodi|Manik|Ajharul"
```

```sql
SELECT * FROM personal
where name regexp "^mahodi|Manik|^Ajharul"
```

```sql
SELECT * FROM personal
where name regexp '[i]'
```

```sql
SELECT * FROM personal
where name regexp '[iskj]a'
```

ia ,sa,ka,ja

```sql
SELECT * FROM personal
where name regexp 'a[iskj]'
```

ai ,as,ak,aj

```sql
SELECT * FROM personal
where name regexp '^[iskj]a'
```

SELECT \* FROM personal
order by name ASC

start a to j and last r

### ORDER BY & DISTINCT

```sql
SELECT * FROM personal
ORDER BY name , age ,.... ASC | DESC
```

```sql
SELECT * FROM personal
order by name DESC
```

```sql
SELECT * FROM personal
Where city = "meherpur"
order by name, age desc;
```

### DISTINCT

```sql
SELECT  DISTNCT column1, column2,column3 FROM student;
```

### IS NULL

```sql
SELECT column1,column2,.... FROM table_name WHERE IS NULL
```

```sql
SELECT column1,column2,.... FROM table_name WHERE IS NOT NULL
```

### SELECT DATA WITH LIMIT

```sql
SELECT column1,column2,.... FROM table_name WHERE condition / opsonal
LIMIT number
```

```sql
SELECT *FROM table_name
LIMIT 2;
```

```sql
SELECT * FROM personal
where city = "kulna"
order by name
 limit 10
```

### OFFSET

```sql
SELECT column1,column2,.... FROM table_name WHERE condition / opsonal
LIMIT offset number
```

```sql
SELECT * FROM personal
where city = "kulna"
order by name
 limit 3 10
```

### SEKECT DATA WITH AGGREGATE Function

0 COUNT
1 MAX
2 MIN
3 SUM
4 AVG

```sql
SELECT COUNT (colmn_name)
FROM table_name
WHERE condition/Opsonal
```

```sql
SELECT MIN(mark) as Mark name,city
FROM table_name
WHERE condition/Opsonal
```

### UPDATE

```sql
UPDATE Personal
SET phone = "2323234"
WHERE id = 5;
```

###### Multipule change

```sql
UPDATE Personal
SET phone = "2323234" , age = 23
WHERE id = 5;
```

###### Multipole change ROW

```sql
UPDATE Personal
SET phone = "2323234" , age = 23
WHERE id IN(3,5);
```

### Commit & Rollback

### Rollback

1. INSERT
2. UPDATESS
3. DELETE

### Rollback Function

```sql
SELECT * FROM personal;
COMMIT;
UPDATE personal SET age = 20;
WHERE id = 3;

ROLLBACK;

```

### DELETE From Tables

```sql
COMMIT;

Delete from personal
where age = 20;

rollback;

```

### PRIMARY KEY

FIRST TIME TABLE CREARE

```sql
CREATE  table_name(
    id INT NULL AUTO_INCREMENT,
    name VARCHAR(30)NOT NULL,
    age INT NOT NULL,
    city VARCHAR(10)NOT NULL
    PRIMARY KEY (id)
)

```

ALLRADY TABLE CREATE A TABLE

```sql
ALTER TABLE table_name
ADD PRIMARY KEY(id)

```

## FOREIGN key comstraint

- A foreign key is a key used to link two tables together.
- A forengn key in one table used to point primary key in another table

### FIRST TIME TABLE CREATE

```sql
CREATE TABLE student(
    id INT NULL AUTO_INCREMENT,
    name   VARCHARE(50)NOT NULL,
    age  INT NOT NULL,
    city VARCHAR(20)NOT NULL,
    PRIMARY KEY (id),
    FOREIGN KEY (city) REFERENCES city(cid)
)

```

#### ALL READY CREAT A TABLE

```sql
   ALTER TABLE table_name
   ADD FOREINGN KEY(city)REFERENCES(cid)
```

### Fack Deta

```sql
CREATE TABLE Students (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    age INT,
    dateofbirth DATE,
    father_name VARCHAR(100),
    mother_name VARCHAR(100),
    city VARCHAR(100),
    phone VARCHAR(20),
    subject VARCHAR(100),
    mark INT,
    student_group VARCHAR(10),
    blood_group VARCHAR(5)
);

INSERT INTO Students (id, name, age, dateofbirth, father_name, mother_name, city, phone, subject, mark, student_group, blood_group) VALUES
(1, 'John Smith', 20, '2004-05-10', 'Michael Smith', 'Emily Smith', 'New York', '123-456-7890', 'Mathematics', 85, 'A', 'O+'),
(2, 'Alice Johnson', 19, '2005-03-15', 'David Johnson', 'Sarah Johnson', 'Los Angeles', '987-654-3210', 'Science', 78, 'B', 'A-'),
(3, 'Emma Brown', 21, '2003-11-20', 'James Brown', 'Olivia Brown', 'Chicago', '234-567-8901', 'Literature', 92, 'A', 'B+'),
(4, 'Ethan Lee', 20, '2004-07-05', 'William Lee', 'Sophia Lee', 'Houston', '345-678-9012', 'History', 80, 'C', 'AB+'),
(5, 'Sophia Wang', 22, '2002-09-30', 'Ethan Wang', 'Grace Wang', 'San Francisco', '456-789-0123', 'Computer Science', 88, 'B', 'A+'),
(6, 'Emily Davis', 19, '2005-01-25', 'Daniel Davis', 'Rachel Davis', 'Seattle', '567-890-1234', 'Chemistry', 79, 'A', 'B-'),
(7, 'Michael Nguyen', 20, '2004-08-12', 'Kevin Nguyen', 'Lisa Nguyen', 'Miami', '678-901-2345', 'Physics', 88, 'B', 'O-'),
(8, 'Olivia Martinez', 21, '2003-06-18', 'Benjamin Martinez', 'Sophia Martinez', 'Dallas', '789-012-3456', 'Economics', 90, 'A', 'A+'),
(9, 'William Garcia', 18, '2006-02-03', 'Jacob Garcia', 'Isabella Garcia', 'Phoenix', '890-123-4567', 'Geography', 85, 'C', 'AB-'),
(10, 'Mia Hernandez', 22, '2002-10-20', 'Alexander Hernandez', 'Ava Hernandez', 'Philadelphia', '901-234-5678', 'English', 92, 'B', 'B+'),
(11, 'Ethan Miller', 19, '2005-04-08', 'Ryan Miller', 'Lily Miller', 'Boston', '012-345-6789', 'Biology', 82, 'A', 'O+'),
(12, 'Chloe Brown', 20, '2004-11-15', 'Matthew Brown', 'Hailey Brown', 'Atlanta', '123-456-7890', 'Mathematics', 87, 'B', 'A-'),
(13, 'Ava Wilson', 21, '2003-07-30', 'Nathan Wilson', 'Victoria Wilson', 'Denver', '234-567-8901', 'Computer Science', 91, 'A', 'B+'),
(14, 'Noah Anderson', 18, '2005-03-05', 'Christopher Anderson', 'Samantha Anderson', 'Detroit', '345-678-9012', 'History', 83, 'C', 'AB+'),
(15, 'Sophia Martinez', 19, '2005-09-10', 'Joshua Martinez', 'Natalie Martinez', 'Chicago', '456-789-0123', 'Literature', 89, 'A', 'A+'),
(16, 'Benjamin Lee', 20, '2004-01-02', 'Andrew Lee', 'Kimberly Lee', 'Houston', '567-890-1234', 'Chemistry', 84, 'B', 'O-'),
(17, 'Mia Rodriguez', 21, '2003-11-07', 'William Rodriguez', 'Ashley Rodriguez', 'Los Angeles', '678-901-2345', 'Physics', 88, 'A', 'B-'),
(18, 'Liam Garcia', 18, '2005-07-22', 'Samuel Garcia', 'Gabriella Garcia', 'San Francisco', '789-012-3456', 'Economics', 90, 'C', 'O+'),
(19, 'Emily Taylor', 22, '2002-05-18', 'John Taylor', 'Rebecca Taylor', 'Seattle', '890-123-4567', 'Geography', 86, 'B', 'A-'),
(20, 'Michael Hernandez', 19, '2005-03-28', 'David Hernandez', 'Samantha Hernandez', 'Miami', '901-234-5678', 'English', 93, 'A', 'B+'),
(21, 'Emma Wilson', 20, '2004-09-14', 'Ethan Wilson', 'Madison Wilson', 'Dallas', '012-345-6789', 'Biology', 85, 'B', 'AB+'),
(22, 'Alexander Kim', 19, '2005-02-19', 'Daniel Kim', 'Chloe Kim', 'Phoenix', '123-456-7890', 'Mathematics', 88, 'A', 'O-'),
(23, 'Olivia Brown', 18, '2006-04-24', 'Joseph Brown', 'Lily Brown', 'Philadelphia', '234-567-8901', 'Chemistry', 91, 'C', 'B+'),
(24, 'Noah Martinez', 21, '2003-08-29', 'Christopher Martinez', 'Evelyn Martinez', 'Boston', '345-678-9012', 'Physics', 84, 'B', 'A-'),
(25, 'Sophia Nguyen', 22, '2002-06-30', 'William Nguyen', 'Sophia Nguyen', 'Denver', '456-789-0123', 'Economics', 89, 'A', 'AB-'),
(26, 'Mia Patel', 19, '2005-12-05', 'Ethan Patel', 'Emily Patel', 'Detroit', '567-890-1234', 'Geography', 92, 'B', 'O+'),
(27, 'Liam Wilson', 20, '2004-10-10', 'Michael Wilson', 'Madison Wilson', 'Chicago', '678-901-2345', 'English', 87, 'A', 'A-'),
(28, 'Emily Kim', 21, '2003-07-15', 'David Kim', 'Grace Kim', 'Houston', '789-012-3456', 'Literature', 90, 'B', 'O-'),
(29, 'Benjamin Brown', 18, '2006-03-20', 'Samuel Brown', 'Natalie Brown', 'San Francisco', '890-123-4567', 'Computer Science', 93, 'C', 'B+'),
(30, 'Ava Johnson', 19, '2005-01-01', 'Benjamin Johnson', 'Hailey Johnson', 'Seattle', '901-234-5678', 'History', 86, 'A', 'AB+'),
(31, 'Noah Lee', 20, '2004-08-16', 'Christopher Lee', 'Madison Lee', 'Miami', '012-345-6789', 'Chemistry', 89, 'B', 'A-'),
(32, 'Mia Rodriguez', 21, '2003-04-21', 'William Rodriguez', 'Sophia Rodriguez', 'Dallas', '123-456-7890', 'Physics', 85, 'A', 'O-'),
(33, 'William Hernandez', 18, '2006-02-28', 'Daniel Hernandez', 'Lily Hernandez', 'Phoenix', '234-567-8901', 'Economics', 92, 'C', 'A+'),
(34, 'Emma Wilson', 22, '2002-11-03', 'Joseph Wilson', 'Chloe Wilson', 'Philadelphia', '345-678-9012', 'Geography', 87, 'B', 'B-'),
(35, 'Liam Kim', 19, '2005-07-08', 'Michael Kim', 'Emily Kim', 'Boston', '456-789-0123', 'English', 90, 'A', 'AB-'),
(36, 'Emily Nguyen', 20, '2004-05-13', 'David Nguyen', 'Grace Nguyen', 'Denver', '567-890-1234', 'Literature', 93, 'B', 'O+'),
(37, 'Benjamin Patel', 21, '2003-09-18', 'Ethan Patel', 'Natalie Patel', 'Detroit', '678-901-2345', 'Computer Science', 88, 'A', 'A-'),
(38, 'Ava Wilson', 18, '2006-01-23', 'Samuel Wilson', 'Sophia Wilson', 'Chicago', '789-012-3456', 'History', 91, 'C', 'B+'),
(39, 'Noah Johnson', 19, '2005-03-28', 'Christopher Johnson', 'Hailey Johnson', 'Houston', '890-123-4567', 'Chemistry', 84, 'B', 'O-'),
(40, 'Sophia Lee', 20, '2004-09-02', 'William Lee', 'Madison Lee', 'San Francisco', '901-234-5678', 'Physics', 87, 'A', 'A+'),
(41, 'Olivia Brown', 21, '2003-11-04', 'Michael Brown', 'Sarah Brown', 'Los Angeles', '012-345-6789', 'Economics', 90, 'A', 'O-'),
(42, 'Ethan Nguyen', 18, '2006-05-17', 'Daniel Nguyen', 'Emma Nguyen', 'Seattle', '123-456-7890', 'Geography', 88, 'B', 'A+'),
(43, 'Mia Martinez', 19, '2005-02-28', 'Joshua Martinez', 'Olivia Martinez', 'Miami', '234-567-8901', 'English', 92, 'A', 'AB-'),
(44, 'Liam Rodriguez', 20, '2004-10-11', 'Benjamin Rodriguez', 'Ava Rodriguez', 'Dallas', '345-678-9012', 'Literature', 87, 'B', 'B-'),
(45, 'Sophia Hernandez', 21, '2003-08-15', 'William Hernandez', 'Emily Hernandez', 'Phoenix', '456-789-0123', 'Computer Science', 93, 'A', 'O+'),
(46, 'Noah Kim', 18, '2006-03-20', 'Christopher Kim', 'Sophia Kim', 'Philadelphia', '567-890-1234', 'History', 84, 'B', 'B+'),
(47, 'Emma Wilson', 19, '2005-01-03', 'Michael Wilson', 'Lily Wilson', 'Boston', '678-901-2345', 'Chemistry', 89, 'A', 'AB-'),
(48, 'Benjamin Brown', 20, '2004-09-14', 'Daniel Brown', 'Grace Brown', 'Detroit', '789-012-3456', 'Physics', 86, 'B', 'O-'),
(49, 'Ava Nguyen', 21, '2003-07-29', 'William Nguyen', 'Natalie Nguyen', 'San Francisco', '890-123-4567', 'Economics', 91, 'A', 'A+'),
(50, 'Noah Martinez', 18, '2006-01-12', 'David Martinez', 'Hailey Martinez', 'Chicago', '901-234-5678', 'Geography', 88, 'B', 'B-'),
(51, 'Mia Johnson', 19, '2005-03-05', 'Joseph Johnson', 'Lily Johnson', 'Houston', '012-345-6789', 'English', 93, 'A', 'O+'),
(52, 'Liam Lee', 20, '2004-11-20', 'Samuel Lee', 'Sophia Lee', 'Los Angeles', '123-456-7890', 'Literature', 88, 'B', 'A-'),

```

### Inner join

the inner join selcts records that have mathching values in both tables

| ID  | Name | age | city |
| --- | ---- | --- | ---- |
| 1   | Ram  | 19  | 1    |
| 2   | khan | 18  | 2    |
| 3   | khan | 18  | 1    |
| 4   | khan | 18  | 3    |

| ID  | city   |
| --- | ------ |
| 1   | agra   |
| 2   | Bhapal |
| 3   | Delhi  |
| 4   | Noida  |

--^
primari key

#### Inner Join Query

```sql
SELECT columns
FROM table1
INNER JOIN table2
ON table1.column_name = table2.column_name

```

##### short name table1 = t1 and table2 =t2

```sql
SELECT columns
FROM table1 t1
INNER JOIN table2 t2
ON t1.column_name = t2.column_name

```

##### show name age rol from table1 and cunty phone show from table2

```sql
SELECT t1.neme,t1.age,t1.rol, t2.cunty,t2,phone
FROM table1 t1
INNER JOIN table2 t2
ON t1.column_name = t2.column_name

```

##### Where used

```sql
SELECT t1.neme,t1.age,t1.rol, t2.cunty,t2,phone
FROM table1 t1
INNER JOIN table2 t2
ON t1.column_name = t2.column_name
WHERE t2.cunty = "Gangni";

```

##### Short name ascending order

```sql
SELECT t1.neme,t1.age,t1.rol, t2.cunty,t2,phone
FROM table1 t1
INNER JOIN table2 t2
ON t1.column_name = t2.column_name
WHERE t2.cunty = "Gangni"
ORDER BY p.name

```

#### LEFT JOIN

The LEFT JOIN in SQL basically returns all records from the left table and the matched records from the right tables. For example, let's say, we have two tables, Table A and Table B. When LEFT JOIN is applied on these two tables, all records from Table A and only the matched records from Table B will be displayed.

#### RIGHT JOIN

Right joins are similar to left joins except they return all rows from the table in the RIGHT JOIN clause and only matching rows from the table in the FROM clause. RIGHT JOIN is rarely used because you can achieve the results of a RIGHT JOIN by simply switching the two joined table names in a LEFT JOIN

#### CROSS JOIN

A cross join returns the Cartesian product of rows from the rowsets in the join. In other words, it will combine each row from the first rowset with each row from the second rowset.

```sql
SELECT columns
FROM table1
CROSS JOIN city
```

#### Inner join syntex for multiple tables

```sql
SELECT columns
FROM table1
INNER JOIN table
ON table1.column_name = table2.coulmn_name
INNER JOIN table3
ON table1.column_name = table3.column_name;

```

##### Where used

```sql
SELECT columns
FROM table1
INNER JOIN table
ON table1.column_name = table2.coulmn_name
INNER JOIN table3
ON table1.column_name = table3.column_name
where table2.cityName = "Dhaka";
```

#### Group by Clause

The group by clause is used in conjunction with the SELECT statement and Aggregate functions to group rows together by common column values.

##### group by syntax

```sql
    SELECT city ,COUNT(city)
    FROM table_name
    WHERE condition
    GROUP BY city

```

#### group 2 table Data too group by

```sql
    SELECT columns COUNT(p.city)
    FROM table1 INNER JOIN table2
    ON table1.column_name = table2.column_name;
    WHERE condition
    GROUP BY column_name
```

#### group Restul

```sql
    SELECT c.cityname, COUNT(p.city)
    FROM personlal p INNER JOIN city c
    ON c.city = p.cid
    GROUP BY city
```

#### group where

where used group by

```sql
    SELECT c.cityname, COUNT(p.city)
    FROM personlal p INNER JOIN city c
    ON c.city = p.cid
    where p.age>=20
    GROUP BY city
```

##### group HAVING

having used group by down

```sql
    SELECT c.cityname, COUNT(p.city)
    FROM personlal p INNER JOIN city c
    ON c.city = p.cid
    GROUP BY city
    HAVING COUNT(p.city) > 3

```

#### SELECT With SubQUery Syntax

```sql
SELECT columns
FROM table1
WHERE
column = (SELECT columns FROM table2 WHERE condition)
```

singel values chack

```sql
SELECT name FROM personal
WHERE courses = (SELECT course_id FROM course WHERE course_name = "BBA");
```

Multipule values
used IN

```sql
SELECT name FROM personal
WHERE courses IN (SELECT course_id FROM course WHERE course_name IN("CSS" "BBA"));
```

#### EXISTS syntex

if any single Record Exists Than parent command show restults

```sql
SELECT columns
FROM table1
WHERE
EXISTS(SELECT columns FROM table2 WHERE condition)
```

#### NO EXISTS syntex

if not any Single Record Exists Than Parent command show results

```sql
SELECT columns
FROM table1
WHERE
NO EXISTS(SELECT columns FROM table2 WHERE condition)
```

#### UNION & UNION ALL syntex

- Each SELECT statement within UNION must have the same number of columns
- The columns must all have similer data types
- The columns is each SELECT statement must alson be in the same order
- number of columns same than used \*

```sql
    SELECT column1, column2 FROM table1
    UNION / UNION ALL
    SELECT column1, column2 FROM table2
```

Normal

```sql
SELECT name FROM students_table WHERE city = "Dhaka"
UNION ALL
SELECT name FROM lecturers_table WHERE city = "MIRPUR"
```

#### UNION to Subquery

```sql
SELECT name FROM students_table
WHERE city = (SELECT cid FROM city WHERE cityname = "DHAKA")
UNION ALL
SELECT name FROM lecturers_table
WHERE city = (SELECT cid FROM city WHERE cityname = "khulna")
```

### IF & CASE statement

#### IF

pass and faill condison chack

```sql
    SELECT id, name,percentage,
    IF(percentage >= 33, "Pass", "Fail") AS Restul
    FROM students
```

#### CASE Clause syntax

Multiple condison
GPA grade

```sql
    SELECT column1, colum2
    CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN condition3 THEN result3
    WHEN condition4 THEN result4
    ELSE result alias_name
    FROM table_name
```

```sql
    SELECT id, name,percentage,
    CASE
        WHEN percentage >=80 AND percentage<=100 THEN "A+"
        WHEN percentage >=65 AND percentage<=79 THEN "A-"
        WHEN percentage >=60 AND percentage<=64 THEN "A"
        WHEN percentage >=55 AND percentage<=59 THEN "B+"
        WHEN percentage >=50 AND percentage<=54 THEN "B"
        WHEN percentage >=40 AND percentage<=49 THEN "B-"
        WHEN percentage >=0 AND percentage<=32 THEN "Fail"
        ELSE "Not Corrent %"
    END AS Grade
    FROM students
```

#### CASE Update

- change columes values 3 and 4

```sql
    UPDATE student SET
    percentage = ( CASE id
        WHEN 3 THEN 39
        WHEN 4 THEN 60
    END
    )
    WHERE id INT (3,7)
```
