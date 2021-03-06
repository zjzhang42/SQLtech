## SQL Cheatsheet
- Insert rows (`INSERT`): 
  - `INSERT INTO table (headers...) VALUES (values...[row1]), (values...[row2]), ..., (values...[rown]);`.

- Select (and Display) rows (`SELECT`): 
  - `SELECT * FROM table;`, `SELECT col_i, col_j FROM table;` (i is not necessarily smaller than j).

- Select unique rows (`DISTINCT`): 
  - `SELECT DISTINCT col_i, col_j FROM table;`.

- Select subsets (`WHERE`): 
  - `SELECT col_i, col_j FROM table WHERE col_k < 0;`, conditions combined with "AND" & "OR".

- Sort rows (`ORDER BY`): 
  - `SELECT col_i, col_j FROM table ORDER BY col_i DESC, col_j ASC;`, rows are sorted based on col_i (descending) and then sorted by col_j (ascending, as default) for the same col_i.

- Update values (`UPDATE`): 
  - `UPDATE table SET col_i='new_value' WHERE col_i='old_value';`.

- Delete rows (`DELETE`): 
  - `DELETE FROM table WHERE col_i='del_value';`.

- Limit results within X rows (`LIMIT`): 
  - `SELECT * FROM table LIMIT X;`.

- Check missing data by using the condition of `IS NULL` and `IS NOT NULL`.

- Loose conditions (`LIKE`): 
  - `SELECT * FROM table WHERE col_i LIKE` `'42%';`/`% _. %;`, where `%` is any series of zero or more characters, `_` is any single character.

- Range conditions (`BETWEEN` and `IN`/`NOT IN`): 
  - `SELECT * FROM table WHERE col_i BETWEEN 10 AND 1000;` and `SELECT * FROM table WHERE col_j (NOT) IN ('A', 'B', 'C');`.

- Concatenate operator (`||`) to connect content from the two columns: 
  - `SELECT col_i || ',' || col_j FROM table;`

- Substring Function: 
  - `SUBSTR(col_i, START_POINT, LENGTH)`, where col_i is a column with STR type.

- Trim Function: 
  - `TRIM(col_i, '., ')` to trim characters (e.g., '.', ',', ' ') from the string, where col_i is a column with STR type.

- Upper/Lower-case Function: 
  - `UPPER()` and `LOWER()`.

- Statistics Function (`COUNT`, `MIN`/`MAX`, `SUM`, `AVG`): 
  - `SELECT COUNT(col_i), MIN(col_i), MAX(col_i), SUM(col_i), AVG(col_i) FROM table where col_i=5;`.

- Grouped statistic results (`GROUP BY`): 
  - `SELECT col_j, SUM(col_i) FROM table GROUP BY col_j;`, `SELECT col_j, col_k, SUM(col_i) FROM table GROUP BY col_j, col_k ORDER BY SUM(col_i) DESC;`.

- Use statistics in WHERE (`HAVING`): 
  - statistics functions cannot be used under `WHERE` but should be used by `HAVING`, appeared after `GROUP BY`. 
  - E.g., `SELECT col_j, col_k, SUM(col_i) FROM table GROUP BY col_j, col_k HAVING SUM(col_i) >= 0 ORDER BY SUM(col_i) DESC;`.

- Subquery parenthesis: 
  - `SELECT * FROM table WHERE col_i = (SELECT MAX(col_i) FROM table);`.

- Link tables: 
  - `FOREIGN KEY (table1_col_i) REFERENCES table2(table2_col_j)`.

- Join tables:
  - `INNER JOIN` returns rows where there is a **match** in both tables. E.g., `SELECT * FROM table1 JOIN table2 ON table1.id=table2.id;`  .
  - `OUTER JOIN` returns non-matching rows.
    - `LEFT OUTER JOIN` returns all rows from the *left-side* table and only matching rows from the *right-side* table.
    - `RIGHT OUTER JOIN` returns all rows from the *right-side* table and only matching rows from the *left-side* table.
    - `FULL OUTER JOIN` returns all rows from both tables.















