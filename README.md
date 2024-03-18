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

    ```sql
        SELECT *
        FROM table_name;
    ```

### chang Name Title Bar

    ```sql
        SELECT id AS ID, name AS "Full Name", age AS Age
        FROM table_name;
    ```

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

    ```sql
        SELECT column1, column2, column3
        FROM table_name
        WHERE condition;
    ```

### Less than or Equal

```sql

SELECT *
From personal
where age <=20;

```
