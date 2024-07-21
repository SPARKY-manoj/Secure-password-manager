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

---
mysql.connector: A Python library that facilitates connecting to MySQL databases.
```python
import mysql.connector
```

Function Definition: dbconfig() is defined to handle the database connection.<br>
Try Block:
mysql.connector.connect(): Attempts to establish a connection to the MySQL database.<br>
Parameters:
host='localhost': Specifies that the database server is running on the local machine.<br>
user='manoj': The username to log into the database.<br>
passwd='MAN#db24': The password associated with the user 'manoj'.<br>
```python
def dbconfig():
    try:
        db = mysql.connector.connect(
            host='localhost',
            user='manoj',
            passwd='MAN#db24'
        )
    except Exception as e:
        console.print_exception(show_locals=True)

    return db
```

dbconfig function to establish a connection to the MySQL database
```python
db = dbconfig()
```
cursor = db.cursor(): Creates a cursor object using the database connection. The cursor object is used to execute SQL queries and fetch results.
```python
cursor = db.cursor()
```
execute function is used to execute the sql queries
```python
cursor.execute(query, data)
```

Commits the transaction to make the changes permanent in the database.
```python
db.commit()
```
It retrieves all (or all remaining) rows of a query result set and returns them as a list of tuples. If no more rows are available, it returns an empty list.
```python
cursor.fetchall()
```
