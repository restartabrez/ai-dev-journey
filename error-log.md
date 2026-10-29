# Error and Solution Log

## 0001 | 2026-10-29 | SQLBolt Lesson 9
- **Tried:** calculate a rating percentage with a join
  `SELECT title, (rating/10)*100 AS rating_percent FROM movies INNER JOIN boxoffice ON movies.id = boxoffice.movie_id;`
- **Happened:** percentage formula was not clear
- **Lesson:** need to think more deeply in simple mathamatical terms before writing the syntax

## 0002 | 2026-10-29 | SQLBolt Lesson 9
- **Tried:** `SELECT title, year FROM movies WHERE year % 2 = 0;`
- **Happened:** I did not know what `%` meant
- **Lesson:** `%` is modulo. It gives the remainder after division. `% 2 = 0` means an even number.

