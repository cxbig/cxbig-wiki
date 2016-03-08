# How to dump a database

## Typical CLI way by `mysqldump`

```sh
# basic syntax
mysqldump [options] my_db > my_db.sql

# compress at the same time
mysqldump [options] my_db | gzip -9 > my_db.sql.gz
```



## Single Transaction

Single transaction will prevent table(s) to be locked. And other queries from application will not be jammed.

```sql
mysqldump --single-transaction my_db > my_db.sql
```



## Inside MySQL client text output

```sql
SELECT * FROM Users
INTO OUTFILE '/path/to/destination/file.csv'
FIELDS TERMINATED BY ','
ENCLOSED BY '"'
LINES TERMINATED BY '\n'
```
_Make sure there is no file exists. No way to rewrite a file from SQL._
