# Problemas SQL HackerRank

---

Problemas SQL HackerRank resueltos solo usando MySQL

## Basic


## MySQL Basic

#### Revising the Select Query I
Query all columns for all American cities in the CITY table with populations larger than 100000.  
The CountryCode for America is USA.

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

SELECT *
FROM city
WHERE countrycode = 'USA'
    AND population > 100000;


#### Revising the Select Query II

Query the **NAME** field for all American cities in the CITY table with populations larger than 120000.  
The CountryCode for America is USA.

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

SELECT name
FROM city
WHERE countrycode = 'USA'
    AND population > 120000;
    
#### Select All

Query all columns (attributes) for every row in the CITY table.

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

SELECT * 
FROM city;

#### Select By ID

Query all columns for a city in CITY with the ID 1661.

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

SELECT *
FROM city
WHERE id = 1661;

#### Japanese Cities' Attributes

Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

SELECT *
FROM city
WHERE countrycode = 'JPN';

#### Japanese Cities' Names

Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
The CITY table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178920595-f0bcf084-18a4-4b12-9079-c3281f1f4352.png)

SELECT name
FROM city
WHERE countrycode = 'JPN';

#### Weather Observation Station 1

Query a list of CITY and STATE from the STATION table.
The STATION table is described as follows:
 
![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

SELECT city, state
FROM station ;

#### Weather Observation Station 3

Query a list of CITY names from STATION for cities that have an even ID number. Print the results in any order, but exclude duplicates
from the answer.
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

SELECT DISTINCT city
FROM station
WHERE (id % 2) = 0 ;

#### Weather Observation Station 4

Find the difference between the total number of CITY entries in the table and the number of distinct CITY entries in the table.
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

For example, if there are three records in the table with CITY values 'New York', 'New York', 'Bengalaru', there are 2 different city
names: 'New York' and 'Bengalaru'. The query returns 1 , because
total number of records - number of unique city names = 3 - 2 = 1.

SELECT count(city) - count(DISTINCT city) as difference
FROM station;

#### Weather Observation Station 5

Query the two cities in STATION with the shortest and longest CITY names, as well as their respective lengths (i.e.: number of characters
in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically.
The STATION table is described as follows:

![image](https://user-images.githubusercontent.com/47682546/178924038-6b808f2b-0b16-45a9-b04a-f92488472687.png)

where LAT_N is the northern latitude and LONG_W is the western longitude.

Sample Input

For example, CITY has four entries: DEF, ABC, PQRS and WXY.

Sample Output

ABC 3
PQRS 4
Explanation

When ordered alphabetically, the CITY names are listed as ABC, DEF, PQRS, and WXY, with lengths  and . The longest name is PQRS, but
there are  options for shortest named city. Choose ABC, because it comes first alphabetically.

Note
You can write two separate queries to get the desired output. It need not be a single query.


## MySQL Intermediate


## MySQL Advanced

