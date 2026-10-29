Query 1: the first 5 movies by length
SELECT title FROM movies
ORDER BY length_minutes ASC
LIMIT 5;
Query 2: movies sorted by title
SELECT title FROM movies
ORDER BY title ASC;
Query 3: movies from one year
SELECT title, year
FROM movies
WHERE year = 2004;
