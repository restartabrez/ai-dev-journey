Date-28 October,2026
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

<B>Date-29 October,2026/
Query1: the title and rating of every movie that has box office data, best rating first.

select title,rating from movies
inner join boxoffice
on movies.id=boxoffice.movie_id
where id is not null
order by rating desc;

Query 2: every movie, including ones with no box office row, with its rating.

select title,rating from movies
left join boxoffice
on movies.id=boxoffice.movie_id;

Query 3: only the movies that have no box office row.

select title from movies
left join boxoffice
on movies.id=boxoffice.movie_id
where movie_id is null;
