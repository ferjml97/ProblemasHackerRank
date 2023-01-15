# Problemas SQL HackerRank

---

Problemas SQL HackerRank resueltos solo usando MySQL

## Basic


## MySQL Basic

#### **Revising the Select Query I**  

Query all columns for all American cities in the CITY table with populations larger than 100000.  
The CountryCode for America is USA.

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

Solution:
```sql
SELECT *
FROM city
WHERE countrycode = 'USA'
    AND population > 100000;
```

#### **Revising the Select Query II**

Query the **NAME** field for all American cities in the CITY table with populations larger than 120000.  
The CountryCode for America is USA.

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

Solution:
```sql
SELECT name
FROM city
WHERE countrycode = 'USA'
    AND population > 120000;
```

#### **Select All**

Query all columns (attributes) for every row in the CITY table.

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

Solution:
```sql
SELECT * 
FROM city;
```

#### **Select By ID**

Query all columns for a city in CITY with the ID 1661.

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

Solution:
```sql
SELECT *
FROM city
WHERE id = 1661;
```

#### **Japanese Cities' Attributes**

Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

Solution:
```sql
SELECT *
FROM city
WHERE countrycode = 'JPN';
```

#### **Japanese Cities' Names**

Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Solution:
```sql
SELECT name
FROM city
WHERE countrycode = 'JPN';
```

#### **Weather Observation Station 1**

Query a list of CITY and STATE from the STATION table.
The STATION table is described as follows:
 
![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

Solution:
```sql
SELECT city, state
FROM station ;
```

#### **Weather Observation Station 3**

Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates
from the answer.
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Solution:
```sql
SELECT DISTINCT city
FROM station
WHERE (id % 2) = 0 ;
```

#### **Weather Observation Station 4**

Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

For example, if there are three records in the table with CITY values 'New York', 'New York', 'Bengalaru',  
there are 2 different city names: 'New York' and 'Bengalaru'. The query returns 1 , because
total number of records - number of unique city names = 3 - 2 = 1.

Solution:
```sql
SELECT count(city) - count(DISTINCT city) as difference
FROM station;
```

#### **Weather Observation Station 5**

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths  
(i.e.: number of characters in the name).  
If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.

The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Sample Input:
For example, CITY has four entries: DEF, ABC, PQRS and WXY.

Sample Output:
ABC 3
PQRS 4
Explanation

When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with lengths  and .  
The longest name is PQRS, but there are  options for shortest named city.  
Choose ABC, because it comes first alphabetically.

Note:
You can write two separate queries to get the desired output. It need not be a single query.

Solution 1:
```sql
SELECT city, length(city) 
FROM station
ORDER BY length(city), city ASC
LIMIT 1;
```

Solution 2:
```sql
SELECT city, length(city) 
FROM station
ORDER BY length(city) DESC
LIMIT 1;
```

#### **Weather Observation Station 6**

Query the list of CITY names starting with vowels (i.e., a, e, i, o, or u) from STATION.  
Your result cannot contain duplicates.

Input Format:
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Solution:
```sql
SELECT DISTINCT city
FROM station
WHERE city REGEXP "^[aeiou].*";
```

#### **Weather Observation Station 7**

Query the list of CITY names ending with vowels (a, e, i, o, u) from STATION. Your result cannot contain duplicates.

Input Format:
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Solution:
```sql
SELECT DISTINCT city
FROM station
WHERE city REGEXP "[aeiou]$";
```

#### **Weather Observation Station 8**

Query the list of CITY names from STATION which have vowels (i.e., a, e, i, o, and u) as both their first and last characters.  
Your result cannot contain duplicates.

Input Format:
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Solution 1:
```sql
SELECT DISTINCT city
FROM station
WHERE city REGEXP "^[aeiou].*[aeiou]$";
```

Solution 2:
```sql
SELECT DISTINCT city
FROM station
WHERE city REGEXP "^[aeiou]" AND city REGEXP "[aeiou]$";
```

#### **Weather Observation Station 9**

Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

Input Format:
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Solution:
```sql
SELECT DISTINCT city
FROM station
WHERE city NOT REGEXP "^[aeiou]";
```

#### **Weather Observation Station 10**

Query the list of CITY names from STATION that do not end with vowels. Your result cannot contain duplicates.

Input Format:
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Solution:
```sql
SELECT DISTINCT city
FROM station
WHERE city NOT REGEXP "[aeiou]$";
```

#### **Weather Observation Station 11**

Query the list of CITY names from STATION that either do not start with vowels or do not end with vowels.  
Your result cannot contain duplicates.

Input Format:
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Solution 1:
```sql
SELECT DISTINCT city
FROM station
WHERE city NOT REGEXP "^[aeiou].*[aeiou]$";
```

Solution 2:
```sql
SELECT DISTINCT city
FROM station
WHERE city NOT REGEXP "^[aeiou]" OR city NOT REGEXP "[aeiou]$";
```

#### **Weather Observation Station 12**

Query the list of CITY names from STATION that do not start with vowels and do not end with vowels.  
Your result cannot contain duplicates.

Input Format:
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Solution:
```sql
SELECT DISTINCT city
FROM station
WHERE city NOT REGEXP "^[aeiou]" AND city NOT REGEXP "[aeiou]$";
```

#### **Higher Than 75 Marks**

Query the Name of any student in STUDENTS who scored higher than  Marks.  
Order your output by the last three characters of each name.  
If two or more students both have names ending in the same last three characters (i.e.: Bobby, Robby, etc.),  
secondary sort them by ascending ID.

Input Format:

![image](https://user-images.githubusercontent.com/47682546/179628750-6bb9d4c2-6b58-48a6-819a-2be9704f2164.png)

The STUDENTS table is described as follows:  The Name column only contains uppercase (A-Z) and lowercase (a-z) letters.

Sample Input:

![image](https://user-images.githubusercontent.com/47682546/179628801-a4acc45c-7275-459e-942c-4c65bc180f63.png)

Sample Output:
Ashley
Julia
Belvet
Explanation

Only Ashley, Julia, and Belvet have Marks > .  
If you look at the last three characters of each of their names, there are no duplicates and 'ley' < 'lia' < 'vet'.

Solution:
```sql
SELECT name
FROM students
WHERE marks > 75
ORDER BY SUBSTRING(NAME, -3), ID ASC;
```

#### **Employee Names**

Write a query that prints a list of employee names (i.e.: the name attribute) from the Employee table in alphabetical order.

Input Format:
The Employee table containing employee data for a company is described as follows:

![image](https://user-images.githubusercontent.com/47682546/179629289-87858a02-e4f9-4f2e-88b1-b298afa86ed6.png)

where employee_id is an employee's ID number, name is their name, months is the total number of months  
they've been working for the company, and salary is their monthly salary.

Sample Input:

![image](https://user-images.githubusercontent.com/47682546/179629306-05efb253-6756-4d8b-8b5c-0f1515db5a47.png)

Sample Output:
Angela
Bonnie
Frank
Joe
Kimberly
Lisa
Michael
Patrick
Rose
Todd

Solution:
```sql
SELECT name
FROM employee
ORDER BY name ASC;
```

#### **Employee Salaries**

Write a query that prints a list of employee names (i.e.: the name attribute) for employees in Employee having a salary greater  
than  per month who have been employees for less than  months. Sort your result by ascending employee_id.

Input Format:
The Employee table containing employee data for a company is described as follows:

![image](https://user-images.githubusercontent.com/47682546/179629845-be68d83c-daaf-41ae-8066-aafe907ad95e.png)

where employee_id is an employee's ID number, name is their name, months is the total number of months  
they've been working for the company, and salary is the their monthly salary.

Sample Input:

![image](https://user-images.githubusercontent.com/47682546/179629879-5f28f03f-a85f-47f3-8f88-0427340b1fe1.png)

Sample Output:
Angela
Michael
Todd
Joe
Explanation

Angela has been an employee for  month and earns $3443 per month.
Michael has been an employee for  months and earns $2017 per month.
Todd has been an employee for  months and earns $3396 per month.
Joe has been an employee for  months and earns $3573 per month.
We order our output by ascending employee_id.

Solution 1:
```sql
SELECT name
FROM employee
WHERE salary > 2000
    AND months < 10
ORDER BY employee_id ASC;
```

---

Solution 2:
```sql
SELECT
FROM station
WHERE
SUBSTR(NAME,-3,3), ID ASC;
ORDER BY RIGHT(NAME, 3), ID ASC;
```

## MySQL Intermediate


## MySQL Advanced

