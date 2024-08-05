Install MySQL server package on app01 using yum.

You can either install Mysql or MariaDB both should work.

SSH into app01 from host01 using command:-

thor@host01~$ ssh app01

````bash
thor@host01 ~$ ssh app01

thor@app01 ~$ sudo yum install  https://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm

thor@app01 ~$ sudo yum install mysql-community-server
````

On app01 start MySQL/MariaDB service on default port.

````bash
thor@app01 ~$ sudo systemctl start mysqld
````

If you have installed MySQL Server then you can find out MySQL root user password using command sudo grep 'temporary password' /var/log/mysqld.log But if you have installed MariaDB server you might have noticed that there is no password set for MySQL root user.

a. If you have installed MariaDB server then set password P@ssw0rd123 for root user.

b. If you have installed MySQL server then change root user password to P@ssw0rd123.

````bash
thor@app01 ~$ sudo grep 'temporary password' /var/log/mysqld.log
    2024-08-05T18:04:38.638594Z 1 [Note] A temporary password is generated for root@localhost: ChYi<lgAr5>q

thor@app01 ~$ mysql -u root -p
    Enter password: 

mysql> SET PASSWORD = PASSWORD('P@ssw0rd123');
    Query OK, 0 rows affected, 1 warning (0.00 sec)

mysql> FLUSH PRIVILEGES;
    Query OK, 0 rows affected (0.00 sec)
````

On app01 server since you have already installed MySQL/MariaDB server and its service is up and running so we created a database kk_db on it.
Login to mysql database server on app01 with password P@ssw0rd123 and identify how many tables kk_db database has.

````bash
mysql> USE kk_db;
Reading table information for completion of table and column names
You can turn off this feature to get a quicker startup with -A

mysql> SHOW Tables;
+-----------------+
| Tables_in_kk_db |
+-----------------+
| MyFamily        |
| MyGuests        |
+-----------------+
2 rows in set (0.00 sec)
````

Create a MySQL user kk_user and set its password to S3cure#3214

````bash
mysql> CREATE USER 'kk_user'@'localhost' IDENTIFIED BY 'S3cure#3214';

    Query OK, 0 rows affected (0.00 sec)
````

Now we already have a database kk_db and a user kk_user. Grant full access on kk_db database to kk_user user.

````bash
mysql> GRANT ALL PRIVILEGES ON kk_db.* TO 'kk_user'@'localhost';

    Query OK, 0 rows affected (0.00 sec)
````