# Use MySQL command line

_please use proper credential for the commands in this file_

## Basic usage for `mysql`

```sh
# basic login
mysql [-h'host'] -u'user' -p'pass'

# run sql command directly
echo 'show databases' | mysql

# import .sql file
mysql my_db < my_db.sql

# import .gz file
gunzip < my_db.sql.gz | mysql
```

## Basic usage for `mysqldump`

```sh
# basic syntax
mysqldump my_db > my_db.sql

# compress at the same time
mysqldump my_db | gzip -9 > my_db.sql.gz
```


## Security

### Use `.my.cnf` file to store credential

To use password in command line is dangerous.  
Keep `-p` without clear password is ok. But to type password everytime is annoying.  
Prepare `.my.cnf` file in your home folder: `/home/cxbig/.my.cnf`

```ini
[client]
user = user_name
password = user_password
```

Then you can run MySQL command without typing user and password.  
**This way is good for normal mysql usage environment. Don't use this method for high security needed databases.**
