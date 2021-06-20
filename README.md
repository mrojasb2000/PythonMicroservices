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

## Global Settings
For change global settings edit admin/settings.py file

1. Setting extension
```
INSTALLED_APPS = [
    ...
    'rest_framework',
    'corsheaders',
    'products'
]

MIDDLEWARE = [
    ...
    'corsheaders.middleware.CorsMiddleware',
    ...
]
```

2. Setting database connection
```
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'admin',
        'USER': 'root',
        'PASSWORD': 'root',
        'HOST': 'db',
        'PORT': '3306',
    }
}
```

3. Setting constant
```
$ CORS_ORIGIN_ALLOW_ALL = True
```

## DB Migrations
For change database settings edit <MODEL>/models.py file

1. Adding mode definition on products/models.py
```
class Product(models.Model):
    title = models.CharField(max_length=200)
    image = models.CharField(max_length=200)
    likes = models.PositiveBigIntegerField(default=0)

class User(models.Model):
    pass    
```

5.- Running migrations

```
$ python manage.py makemigrations

$ python manage.py migrate
```

6.- List tables from database
```
mysql> show tables;
+----------------------------+
| Tables_in_admin            |
+----------------------------+
| auth_group                 |
| auth_group_permissions     |
| auth_permission            |
| auth_user                  |
| auth_user_groups           |
| auth_user_user_permissions |
| django_admin_log           |
| django_content_type        |
| django_migrations          |
| django_session             |
| products_product           |
| products_user              |
+----------------------------+
12 rows in set (0,01 sec)

```


```
$ 
```
