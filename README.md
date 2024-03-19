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
