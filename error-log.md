# Error and Solution Log

## 0001 | 2026-10-29 | SQLBolt Lesson 9
- **Tried:** calculate a rating percentage with a join
  `SELECT title, (rating/10)*100 AS rating_percent FROM movies INNER JOIN boxoffice ON movies.id = boxoffice.movie_id;`
- **Happened:** percentage formula was not clear
- **Lesson:** (rating / 10) * 100 turns a score out of 10 into a percentage. Write the formula in plain maths first (for example 8.2 out of 10 is 82 percent), then translate it into SQL. AS rating_percent gives the new column a readable name.
## 0002 | 2026-10-29 | SQLBolt Lesson 9
- **Tried:** `SELECT title, year FROM movies WHERE year % 2 = 0;`
- **Happened:** I did not know what `%` meant
- **Lesson:** `%` is modulo. It gives the remainder after division. `% 2 = 0` means an even number.
## 0003 | 2026-10-29 | Text in quotes
- **Tried:** `WHERE country = "United States"`
- **Happened:** it worked in SQLBolt
- **Lesson:** in PostgreSQL (Supabase), text goes in single quotes, `'United States'`. Double quotes are for column and table names.
## 0004 | 2026-10-29 | With one movie per year 
- **Tried:** confusion in answering 
- **Happened:** As each year has only one release in Movies table
- **Lesson:** Use a range to see sorting.” That is a good real lesson: always test a query on data where the answer can be seen.
