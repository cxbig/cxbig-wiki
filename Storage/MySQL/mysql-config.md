# MySQL config

## my.cnf

### `innodb_file_per_table` in `mysqld`

By default, this value is 0. After a long time use, MySQL will accumulate huge amount of content in file like `ibdata1`.

**Highly suggest to change to 1 as quick as possible**

```ini
; my.cnf
[mysqld]
innodb_file_per_table=1
```






































<fin>
