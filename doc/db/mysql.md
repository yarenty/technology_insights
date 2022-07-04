# mysql
We've installed your MySQL database without a root password. To secure it run:
mysql_secure_installation

MySQL is configured to only allow connections from localhost by default

To connect run:
```shell
mysql -uroot
```

To restart mysql after an upgrade:
```shell
brew services restart mysql
```
Or, if you don't want/need a background service you can just run:

```shell
/usr/local/opt/mysql/bin/mysqld_safe --datadir=/usr/local/var/mysql
```