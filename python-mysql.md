This is MySQL Python programming tutorial. It covers the basics of MySQL programming with Python. It uses the MySQLdb module. The examples were created and tested on Ubuntu Linux.

# MySQLdb install
---
Here we install the Python interface to the MySQL database
```linux-terminal
sudo apt-get install python-mysqldb
```
---
Here the command installs the MySQL server and various other packages.
```
sudo apt-get install mysql-server
```
While installing the package, we are prompted to enter a password for the MySQL root account.

---
To get into the mysql interface
```
mysql -u root
```

---
Now to create a database
```
 CREATE DATABASE testdb
```

---
Creates a new MySQL user named testuser with a password of test623. This user will only be able to connect to the MySQL server from the local machine (localhost).
```
CREATE USER 'testuser'@'localhost' IDENTIFIED BY 'test623'
```
Grants all privileges to the user ‘testuser’ on the database ‘testdb’ when connecting from the local host ‘localhost’.
```
GRANT ALL ON testdb.* TO 'testuser'@'localhost'
```


