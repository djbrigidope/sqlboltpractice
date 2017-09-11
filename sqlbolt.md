# Practicing Sql with sql bolt
## Initial Table Results:
```
Id	Title	Director	Year Length_minutes
1	Toy Story	John Lasseter	1995	81
2	A Bug's Life	John Lasseter	1998	95
3	Toy Story 2	John Lasseter	1999	93
4	Monsters, Inc.	Pete Docter	2001	92
5	Finding Nemo	Andrew Stanton	2003	107
6	The Incredibles	Brad Bird	2004	116
7	Cars	John Lasseter	2006	117
8	Ratatouille	Brad Bird	2007	115
9	WALL-E	Andrew Stanton	2008	104
10	Up	Pete Docter	2009	101
11	Toy Story 3	Lee Unkrich	2010	103
12	Cars 2	John Lasseter	2011	120
13	Brave	Brenda Chapman	2012	102
14	Monsters University	Dan Scanlon	2013	110

```
#### find title of each movie

```
SELECT title FROM movies;

Table: Movies
Title
Toy Story
A Bug's Life
Toy Story 2
Monsters, Inc.
Finding Nemo
The Incredibles
Cars
Ratatouille
WALL-E
Up
Toy Story 3
Cars 2
Brave
Monsters University
RESET

```
#### find director for each film
```
SELECT director FROM movies;
Table: Movies
Director
John Lasseter
John Lasseter
John Lasseter
Pete Docter
Andrew Stanton
Brad Bird
John Lasseter
Brad Bird
Andrew Stanton
Pete Docter
Lee Unkrich
John Lasseter
Brenda Chapman
Dan Scanlon
RESET
```
#### find title and year of fils from movies
```
SELECT title, director FROM movies;

Title	Director
Toy Story	John Lasseter
A Bug's Life	John Lasseter
Toy Story 2	John Lasseter
Monsters, Inc.	Pete Docter
Finding Nemo	Andrew Stanton
The Incredibles	Brad Bird
Cars	John Lasseter
Ratatouille	Brad Bird
WALL-E	Andrew Stanton
Up Pete Docter
```
#### find the title and  year of each film
```
SELECT title, year FROM movies;

Title	Year
Toy Story	1995
A Bug's Life	1998
Toy Story 2	1999
Monsters, Inc.	2001
Finding Nemo	2003
The Incredibles	2004
Cars	2006
Ratatouille	2007
WALL-E	2008
Up	2009
```

#### Find all the information about each film
```
SELECT * FROM movies;

Id	Title	Director	Year	Length_minutes
1	Toy Story	John Lasseter	1995	81
2	A Bug's Life	John Lasseter	1998	95
3	Toy Story 2	John Lasseter	1999	93
4	Monsters, Inc.	Pete Docter	2001	92
5	Finding Nemo	Andrew Stanton	2003	107
6	The Incredibles	Brad Bird	2004	116
7	Cars	John Lasseter	2006	117
8	Ratatouille	Brad Bird	2007	115
9	WALL-E	Andrew Stanton	2008	104
10	Up	Pete Docter	2009	101
```

## Select Query With Constraints
```
SELECT column, another column, ...
FROM mytable
WHERE condition
 AND/OR anotherCondition
 AND/OR ...;
 ```
Construct complex clauses by joining numerous AND OR logic keywords.
```
num_wheels >= 4 AND doors <=2
```
operators for building queries:
Operator
Condition
SQL Example
**********************
```=, !=, < <=, >, >=```
Standard numerical operators
col_name != 4
**********************

```BETWEEN … AND …```
Number is within range of two values (inclusive)

col_name BETWEEN 1.5 AND 10.5

```NOT BETWEEN … AND …```
Number is not within range of two values (inclusive)

col_name NOT BETWEEN 1 AND 10

```IN (…)```
Number exists in a list

col_name IN (2, 4, 6)

```NOT IN (…)```
Number does not exist in a list

col_name NOT IN (1, 3, 5)

****************************

#### Find the movie with a row  id of 6
```
SELECT id, title FROM movies WHERE id = 6;

Id	Title
6	The Incredibles
```
#### Find the movies released in the years between 2000 and 2010
```
SELECT title FROM movies WHERE year BETWEEN 2000 and 2010;

Title
Monsters, Inc.
Finding Nemo
The Incredibles
Cars
Ratatouille
WALL-E
Up
Toy Story 3
```
#### Find the movies not released in the years between 2000 and 2010
```
SELECT title FROM movies WHERE year NOT BETWEEN 2000 and 2010;

Title
Toy Story
A Bug's Life
Toy Story 2
Cars 2
Brave
Monsters University
```
#### Find the movie with a row  id of 6
```
SELECT title FROM movies WHERE id = 6;
Title
The Incredibles
```
#### Find the movies released in the years between 2000 and 2010
```
SELECT title FROM movies WHERE year between 2000 and 2010;
```
#### Find the movies not released in the years between 2000 and 2010
```
SELECT title FROM movies WHERE year NOT between 2000 and 2010;

Table: Movies
Title
Toy Story
A Bug's Life
Toy Story 2
Cars 2
Brave
Monsters University
```
#### Find the first 5 Pixar movies and their release year
```
SELECT title, year FROM movies
WHERE year <= 2003;

Title	Year
Toy Story	1995
A Bug's Life	1998
Toy Story 2	1999
Monsters, Inc.	2001
Finding Nemo	2003
```

#### Find all the Toy Story movies
```
SELECT * FROM movies WHERE title LIKE "Toy Story%";

Id	Title	Director	Year	Length_minutes
1	Toy Story	John Lasseter	1995	81
3	Toy Story 2	John Lasseter	1999	93
11	Toy Story 3	Lee Unkrich	2010	103

```
#### Find all the movies directed by John Lasseter
```
SELECT * FROM movies WHERE director LIKE "John La%";

Id	Title	Director	Year	Length_minutes
1	Toy Story	John Lasseter	1995	81
2	A Bug's Life	John Lasseter	1998	95
3	Toy Story 2	John Lasseter	1999	93
7	Cars	John Lasseter	2006	117
12	Cars 2	John Lasseter	2011	120
```
#### Find all the movies (and director) not directed by John Lasseter
```
SELECT * FROM movies WHERE director NOT LIKE "John La%";

Id	Title	Director	Year	Length_minutes
4	Monsters, Inc.	Pete Docter	2001	92
5	Finding Nemo	Andrew Stanton	2003	107
6	The Incredibles	Brad Bird	2004	116
8	Ratatouille	Brad Bird	2007	115
9	WALL-E	Andrew Stanton	2008	104
10	Up	Pete Docter	2009	101
11	Toy Story 3	Lee Unkrich	2010	103
13	Brave	Brenda Chapman	2012	102
14	Monsters University	Dan Scanlon	2013	110
87	WALL-G	Brenda Chapman	2042	97
```
#### Find all the WALL-* movies
```
SELECT * FROM movies WHERE title LIKE "Wall-%";

Id	Title	Director	Year	Length_minutes
9	WALL-E	Andrew Stanton	2008	104
87	WALL-G	Brenda Chapman	2042	97
```
#### List all directors of Pixar movies (alphabetically), without duplicates
```
SELECT DISTINCT director from movies ORDER BY director ASC;

Director
Andrew Stanton
Brad Bird
Brenda Chapman
Dan Scanlon
John Lasseter
Lee Unkrich
Pete Docter

```
#### List the last four Pixar movies released (ordered from most recent to least)
```
SELECT title, year FROM movies
ORDER BY year DESC
LIMIT 4;


Title	Year
Monsters University	2013
Brave	2012
Cars 2	2011
Toy Story 3	2010
```
#### List the first five Pixar movies sorted alphabetically
```
SELECT title, year FROM movies
ORDER BY title ASC
LIMIT 5;

Title	Year
A Bug's Life	1998
Brave	2012
Cars	2006
Cars 2	2011
Finding Nemo	2003
```
#### List the next five Pixar movies sorted alphabetically
```
SELECT title, year FROM movies
ORDER BY title ASC
LIMIT 5 OFFSET 5;

Title	Year
Monsters University	2013
Monsters, Inc.	2001
Ratatouille	2007
The Incredibles	2004
Toy Story	1995
```

## INITIAL TABLE RESULTS 2
```
Table: North_american_cities
City	Country	Population	Latitude	Longitude
Guadalajara	Mexico	1500800	20.659699	-103.349609
Toronto	Canada	2795060	43.653226	-79.383184
Houston	United States	2195914	29.760427	-95.369803
New York	United States	8405837	40.712784	-74.005941
Philadelphia	United States	1553165	39.952584	-75.165222
Havana	Cuba	2106146	23.05407	-82.345189
Mexico City	Mexico	8555500	19.432608	-99.133208
Phoenix	United States	1513367	33.448377	-112.074037
Los Angeles	United States	3884307	34.052234	-118.243685
Ecatepec de Morelos	Mexico	1742000	19.601841	-99.050674
Montreal	Canada	1717767	45.501689	-73.567256
Chicago	United States	2718782	41.878114	-87.629798
```

#### List all the Canadian cities and their populations
```
SELECT city, population FROM north_american_cities
WHERE country = "Canada";

City	Population
Toronto	2795060
Montreal	1717767
```

#### Order all the cities in the United States by their latitude from north to south
```
SELECT city, latitude FROM north_american_cities
WHERE country = "United States"
ORDER BY latitude DESC;



City	Latitude
Chicago	41.878114
New York	40.712784
Philadelphia	39.952584
Los Angeles	34.052234
Phoenix	33.448377
Houston	29.760427
```
#### List all the cities west of Chicago, ordered from west to east
```
SELECT city, longitude FROM north_american_cities
WHERE longitude < -87.629798
ORDER BY longitude ASC;

City	Longitude
Los Angeles	-118.243685
Phoenix	-112.074037
Guadalajara	-103.349609
Mexico City	-99.133208
Ecatepec de Morelos	-99.050674
Houston	-95.369803
```
#### List the two largest cities in Mexico (by population)
```
SELECT * FROM north_american_cities
WHERE country = "Mexico"
ORDER BY population DESC
LIMIT 2
;
```
#### List the two largest cities in Mexico (by population)
```

SELECT * FROM north_american_cities
WHERE country = "Mexico"
ORDER BY population DESC
LIMIT 2
;

```


#### List the third and fourth largest cities (by population) in the United States and their population

```
SELECT city, population FROM north_american_cities
WHERE country LIKE "United States"
ORDER BY population DESC
LIMIT 2 OFFSET 2;

City	Population
Chicago	2718782
Houston	2195914

```
#### List all directors of Pixar movies (alphabetically), without duplicates
```
SELECT DISTINCT director FROM movies
OORDER BY director ASC;

Table: Movies
Director
Andrew Stanton
Brad Bird
Brenda Chapman
Dan Scanlon
John Lasseter
Lee Unkrich
Pete Docter
```

#### List the last four Pixar movies released (ordered from most recent to least)
```
SELECT title, year FROM movies
ORDER BY year DESC
LIMIT 4;
```

#### List the first five Pixar movies sorted alphabetically
```
SELECT title, year FROM movies
ORDER BY title ASC
LIMIT 5;
```
#### List the next five Pixar movies sorted alphabetically
```
SELECT title, year FROM movies
ORDER BY title ASC
LIMIT 5 OFFSET 5;

Title	Year
Monsters University	2013
Monsters, Inc.	2001
Ratatouille	2007
The Incredibles	2004
Toy Story	1995
```
