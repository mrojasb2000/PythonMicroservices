## Make commands

Startup services containers
```
$ make up
```

Shutdown services
```
$ make down
```

Execute shell on container
```
$ make sh
```


## Connect to databse MySQL

For connect to MySQL database server, using mysql-client

```
$ mysql -h 127.0.0.1 -P 33066 -u root -p
Enter password: 
Welcome to the MySQL monitor.  Commands end with ; or \g.
Your MySQL connection id is 2
Server version: 5.7.22 MySQL Community Server (GPL)

Copyright (c) 2000, 2021, Oracle and/or its affiliates.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.

mysql>
```