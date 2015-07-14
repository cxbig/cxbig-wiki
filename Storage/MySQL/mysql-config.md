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

#### How to resolve when I used for a long time:

1. Dump all your databases
2. Stop MySQL server
3. Update config
4. Remove `ibdata1`, `ibdata2` maybe you have...
5. Start MySQL server
6. Import all your databases





































<fin>
