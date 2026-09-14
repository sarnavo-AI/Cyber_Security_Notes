_Structured Query Language_ (SQL) has been developed specifically to manage and interact with data stored inside [_relational databases_](https://en.wikipedia.org/wiki/Relational_database). SQL can be employed to query, insert, modify, or even delete data, and, in some cases, execute operating system commands. Since the SQL instance offers so many administrative privileges, we'll soon observe how arbitrary SQL queries can pose a significant security risk.

```
<?php
$uname = $_POST['uname'];
$passwd = $_POST['password'];

$sql_query = "SELECT * FROM users WHERE user_name= '$uname' AND password='$passwd'";
$result = mysqli_query($con, $sql_query);
?>
```


Highlighted above is a semi-precompiled SQL query that searches the users table for the provided username and its respective password, which are saved into the _uname_ and _passwd_ variables. The query string is then stored in _sql_query_ and used to perform the query against the local database through the [_mysqli_query_](https://www.php.net/manual/en/mysqli.query.php) function, which saves the result of the query in _$result_.

Many DB variants differ in syntax, function, and features. In this section, we are going to focus on two of the most common database variants, MySQL and Microsoft SQL Server (MSSQL).

[_MySQL_](https://www.mysql.com/) is one of the most deployed database variants, along with [_MariaDB_](https://mariadb.org/), an open-source fork of MySQL.

### Note the -p'root', if you type it like -p root, it will prompt for password and assume the root is the db name, so always write -p'root' or -proot but NOT -p root. 
```
kali@kali:~$ mysql -u root -p'root' -h 192.168.50.16 -P 3306 --skip-ssl-verify-server-cert

Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

MySQL [(none)]>
```

```
MySQL [(none)]> select version();
+-----------+
| version() |
+-----------+
| 8.0.21    |
+-----------+
1 row in set (0.107 sec)
```

We can also verify the current database user for the ongoing session via the _system_user()_ function, which returns the current username and hostname for the MySQL connection.

```
MySQL [(none)]> select system_user();
+--------------------+
| system_user()      |
+--------------------+
| root@192.168.20.50 |
+--------------------+
1 row in set (0.104 sec)
```

