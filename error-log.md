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
