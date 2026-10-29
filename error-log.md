SQL Bolt :Date-29/10
Error log0001 - chapter9
SELECT title,(rating/10)*100 as rating_percent FROM movies
inner join boxoffice
on movies.id=boxoffice.movie_id;

SQL Bolt :Date-29/10
Error log0001 - chapter9
SELECT title, year
FROM movies
WHERE year % 2 = 0;
