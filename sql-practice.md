## Date: 28 October 2026

### Query 1: the first 5 movies by length

```sql
SELECT title FROM movies
ORDER BY length_minutes ASC
LIMIT 5;
```

### Query 2: movies sorted by title

```sql
SELECT title FROM movies
ORDER BY title ASC;
```

### Query 3: movies from one year

```sql
SELECT title, year
FROM movies
WHERE year = 2004;
```

## Date: 29 October 2026

### Query 1: title and rating of every movie that has box office data, best rating first

```sql
SELECT title, rating FROM movies
INNER JOIN boxoffice
ON movies.id = boxoffice.movie_id
ORDER BY rating DESC;
```

### Query 2: every movie, including ones with no box office row, with its rating

```sql
SELECT title, rating FROM movies
LEFT JOIN boxoffice
ON movies.id = boxoffice.movie_id;
```

### Query 3: only the movies that have no box office row

```sql
SELECT title FROM movies
LEFT JOIN boxoffice
ON movies.id = boxoffice.movie_id
WHERE boxoffice.movie_id IS NULL;
```

**INNER JOIN keeps only rows that match in both tables, but LEFT JOIN keeps ___.**
