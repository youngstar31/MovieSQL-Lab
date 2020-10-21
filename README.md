# MovieSQL-Lab

## Create a query to find all movies in the Sci-Fi genre.

SELECT * FROM movietheater
 WHERE genre = 'Sci-Fi';



## Create a query to find all films that scored at least a 6.5 on IMDB

 SELECT * FROM movietheater
 WHERE imdb_score >= 6.5;



## For parents who have young kids, but who don't want to sit through long children's movies, create a query to find all of the movies rated G or PG that are less than 100 minutes long.

 SELECT * FROM movietheater
 WHERE rating = 'G' OR 'PG' AND runtime < 100;



## Create a query to show the average runtimes of movies scoring below a 7.5 on imdb, grouped by their respective genres.

SELECT genre, AVG(runtime)
FROM movietheater
WHERE imdb_score < 7.5
GROUP BY genre;


## Show the ID number and rating of all of the Horror and Documentary movies in the database. Do this in only one query.

SELECT rating FROM movietheater
WHERE genre IN ('Horror', 'Documentary');



## There's been a data entry mistake; Starship Troopers is actually rated R, not PG-13. Create a query that finds the movie by its title and changes its rating to R.


UPDATE movietheater
SET rating = 'R'
WHERE title = 'Starship Troopers';




## This time let's find the average, maximum, and minimum IMDB score for movies of each rating.



SELECT rating, MAX(imdb_score), MIN(imdb_score), AVG(imdb_score)
FROM movietheater
GROUP BY rating;




## That last query isn't very informative for ratings that only have 1 entry. Use a HAVING COUNT(*) > 1 clause to only show ratings with multiple movies showing.


SELECT rating, MAX(imdb_score), MIN(imdb_score), AVG(imdb_score)
FROM movietheater
GROUP BY rating 
HAVING COUNT(*) > 1;









