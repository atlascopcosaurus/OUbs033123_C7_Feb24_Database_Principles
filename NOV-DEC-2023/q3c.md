Let's start by creating the database schema for the `Passenger` table as per the provided schema. After the table is created, we'll proceed with SQL statements for each of your specified queries.

### Create the Database 
 Once you're connected to the MariaDB server, you can create a new database by executing the CREATE DATABASE SQL statement. For example, if you want to create a database named AirlineDB, you would run:

```sql
CREATE DATABASE AirlineDB;
```

### Select the Database for Use

 After creating your database, you can start using it to create tables and perform other operations by selecting it with the USE statement:

```sql
USE AirlineDB;
```

### Creating the `Passenger` Table

To create the `Passenger` table within your MariaDB database, you would use the following SQL statement:

```sql
CREATE TABLE Passenger (
    pid INT PRIMARY KEY,
    pname VARCHAR(255),
    address VARCHAR(255),
    age INT,
    gender VARCHAR(10),
    destination VARCHAR(255),
    booking VARCHAR(50),
    ticket VARCHAR(50),
    departure_date DATE,
    departure_time TIME,
    payment_mode VARCHAR(50),
    amount_paid DECIMAL(10, 2)
);
```

### Queries Based on Your Requests

Now, let's address each of your requests with an appropriate SQL statement.

#### i. List the name of passengers taking off to “London.”

```sql
SELECT pname
FROM Passenger
WHERE destination = 'London';
```

#### ii. List the male passengers whose bookings were confirmed.

```sql
SELECT pname
FROM Passenger
WHERE gender = 'Male' AND booking = 'Confirmed';
```

#### iii. Display the name and age of the passengers taking off to Dubai or Bombay.

```sql
SELECT pname, age
FROM Passenger
WHERE destination IN ('Dubai', 'Bombay');
```

#### iv. List the details of all passengers whose name starts with "b" and ends with "y".

```sql
SELECT *
FROM Passenger
WHERE pname LIKE 'b%y';
```

#### v. Display details of female passengers whose payments were between 35000 and 75000.

```sql
SELECT *
FROM Passenger
WHERE gender = 'Female' AND amount_paid BETWEEN 35000 AND 75000;
```

#### vi. Display details of passengers whose tickets were not issued and their date of departure is on 30/11/2023.

```sql
SELECT *
FROM Passenger
WHERE ticket IS NULL OR ticket = '' AND departure_date = '2023-11-30';
```

#### vii. List the gender and age of staff whose payment is greater than Rs 50000 in descending order of address.

It seems there might be a slight mistake in the request as it mentions "staff," but the schema provided only concerns "Passengers." Assuming the request was meant for passengers, the corrected query would be:

```sql
SELECT gender, age
FROM Passenger
WHERE amount_paid > 50000
ORDER BY address DESC;
```

These SQL statements should help you manipulate and query the `Passenger` table in your MariaDB database according to your specific requests. If you have further questions or need assistance with another SQL topic, feel free to ask!