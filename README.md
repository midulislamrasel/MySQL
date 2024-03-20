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

## Commit & Rollback

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

### FOREIGN key comstraint

- A foreign key is a key used to link two tables together.
- A forengn key in one table used to point primary key in another table

##### FIRST TIME TABLE CREATE

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

##### ALL READY CREAT A TABLE

```sql
   ALTER TABLE table_name
   ADD FOREINGN KEY(city)REFERENCES(cid)
```

```sql
INSERT INTO students (id, name, age, dateofbirth, father_name, mother_name, city, phone, subject, mark, student_group, blood_group)
VALUES
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
(20, 'Michael Hernandez', 19, '2005-03-28', 'David Hernandez', 'Samantha Hernandez', 'Miami', '901-234-5678', 'English', 93, 'A', 'B+');
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
(40, 'Sophia Lee', 20, '2004-09-02', 'William Lee', 'Madison Lee', 'San Francisco', '901-234-5678', 'Physics', 87, 'A', 'A+');
```
