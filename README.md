### Weather Observation Station 3

Query a list of **CITY** names from **STATION** for cities that have an even ID number. Print the results in any order, but exclude duplicates from the answer.

The **STATION** table is described as follows:

| Field  | Type |
| ------------- | ------------- |
| ID  | NUMBER  |
| CITY  | VARCHAR2(21)  |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER  |
| LONG_W  | NUMBER  |

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

*Solution*

```sql
SELECT DISTINCT CITY
FROM STATION
WHERE ID % 2 = 0 
ORDER BY CITY ASC ;
```


### Weather Observation Station 4

Find the difference between the total number of **CITY** entries in the table and the number of distinct **CITY** entries in the table.

The **STATION** table is described as follows:

| Field  | Type |
| ------------- | ------------- |
| ID  | NUMBER  |
| CITY  | VARCHAR2(21)  |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER  |
| LONG_W  | NUMBER  |

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

*Solution*

```sql
SELECT COUNT(CITY) - COUNT(DISTINCT CITY) 
FROM STATION ;
```


### Weather Observation Station 5

Query the two cities in **STATION** with the shortest and longest **CITY** names, as well as their respective lengths (i.e.: number of characters in the name). If there is more than one smallest or largest city, choose the one that comes first when ordered alphabetically. You can write two separate queries to get the desired output, it need not be a single query.

The **STATION** table is described as follows:

| Field  | Type |
| ------------- | ------------- |
| ID  | NUMBER  |
| CITY  | VARCHAR2(21)  |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER  |
| LONG_W  | NUMBER  |

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

*Solution*

```sql
SELECT CITY, length(CITY) 
FROM STATION 
ORDER BY length(CITY), CITY limit 1;
```

```sql
SELECT CITY, length(CITY) 
FROM STATION 
ORDER BY length(CITY) DESC, CITY limit 1 ;
```


### Weather Observation Station 6

Query the list of **CITY** names starting with vowels (i.e., a, e, i, o, or u) from **STATION**. Your result cannot contain duplicates.

The **STATION** table is described as follows:

| Field  | Type |
| ------------- | ------------- |
| ID  | NUMBER  |
| CITY  | VARCHAR2(21)  |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER  |
| LONG_W  | NUMBER  |

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

*Solution*

```sql
SELECT CITY 
FROM STATION 
WHERE LEFT(CITY, 1) IN ('a', 'e', 'i', 'o', 'u') ; 
```


### Weather Observation Station 7 

Query the list of **CITY** names ending with vowels (a, e, i, o, u) from **STATION**. Your result cannot contain duplicates.

The **STATION** table is described as follows:

| Field  | Type |
| ------------- | ------------- |
| ID  | NUMBER  |
| CITY  | VARCHAR2(21)  |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER  |
| LONG_W  | NUMBER  |

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

*Solution*

```sql
SELECT DISTINCT CITY 
FROM STATION 
WHERE RIGHT(CITY, 1) IN ('a', 'e', 'i', 'o', 'u') ; 
```


### Weather Observation Station 8

Query the list of **CITY** names from **STATION** which have vowels (i.e., a, e, i, o, and u) as both their first and last characters. Your result cannot contain duplicates. 

The **STATION** table is described as follows:

| Field  | Type |
| ------------- | ------------- |
| ID  | NUMBER  |
| CITY  | VARCHAR2(21)  |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER  |
| LONG_W  | NUMBER  |

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

*Solution* 

```sql
SELECT DISTINCT CITY
FROM STATION 
WHERE RIGHT(CITY, 1) IN ('a', 'e', 'i', 'o', 'u') AND LEFT(CITY, 1) IN ('a', 'e', 'i', 'o', 'u') ; 
```


### Weather Observation Station 9

Query the list of CITY names from STATION that do not start with vowels. Your result cannot contain duplicates.

The **STATION** table is described as follows:

| Field  | Type |
| ------------- | ------------- |
| ID  | NUMBER  |
| CITY  | VARCHAR2(21)  |
| STATE  | VARCHAR2(2)  |
| LAT_N  | NUMBER  |
| LONG_W  | NUMBER  |

where **LAT_N** is the northern latitude and **LONG_W** is the western longitude.

*Solution* 

```sql
SELECT DISTINCT CITY 
FROM STATION 
WHERE LEFT(CITY,1) NOT IN ('a','e','i','o','u') ; 
```

