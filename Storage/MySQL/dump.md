# How to dump a database

## Typical CLI way by `mysqldump`

```sh
# basic syntax
mysqldump [options] my_db > my_db.sql

# compress at the same time
mysqldump [options] my_db | gzip -9 > my_db.sql.gz
```



## Inside MySQL client text output

```sql
SELECT * FROM Users
INTO OUTFILE '/path/to/destination/file.csv'
FIELD TERMINATED BY ','
ENCLOSED BY '"'
LINE TERMINATED BY '\n'
```
_Make sure there is no file exists. No way to rewrite a file from SQL._
