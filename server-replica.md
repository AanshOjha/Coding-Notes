1. Create a azure vm

2. install mysql 

3. become superuser 
* oif u are superuser, no need of `sudo`
```
sudo su
```

4. edit
```
nano /etc/mysql/my.cnf
```

5. enter this

```
[mysqld]
log-bin=mysql-bin
server-id=1
```

6. 
```
sudo systemctl status mysql
```

7. 
```
mysql -u root -p
```

8. insert dome data in a db

9. 
```
CREATE USER 'replication_user'@'%' IDENTIFIED BY 'password';
GRANT REPLICATION SLAVE ON *.* TO 'replication_user'@'%';
FLUSH PRIVILEGES;
exit;
```

10. login gain to mysql
```
SHOW MASTER STATUS;


+---------------+----------+--------------+------------------+-------------------+
| File          | Position | Binlog_Do_DB | Binlog_Ignore_DB | Executed_Gtid_Set |
+---------------+----------+--------------+------------------+-------------------+
| binlog.000003 |     2143 |              |                  |                   |
+---------------+----------+--------------+------------------+-------------------+

```

# in slave vm

1. nano /etc/mysql/my.cnf

2. add this 
```
[mysqld]
server-id = 2
``` 
save.

3. 






sudo mysql -u root
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
FLUSH PRIVILEGES;
EXIT;

[mysqld]
server-id = 2



CHANGE MASTER TO
MASTER_HOST='98.70.65.59',
MASTER_USER='replication_user',
MASTER_PASSWORD='Password@123',
MASTER_LOG_FILE='mysql-bin.000001',
MASTER_LOG_POS=1695;



STOP SLAVE;
CHANGE MASTER TO MASTER_PASSWORD='Password@123';
START SLAVE;



| log_bin_basename                               | /var/lib/mysql/mysql-bin   
All logs stored here in this file 