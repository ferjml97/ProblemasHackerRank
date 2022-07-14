# ProblemasHackerRank

---

Problemas HackerRank

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


    
## MySQL Intermediate


## MySQL Advanced

