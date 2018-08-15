## Installation and Configuration

### MySQL

#### Installation

...

<br/>

#### Configuration

...

- serverTimezone \<Unfinished\>

*Tomcat would throw this error when starting the app*,

> **WARNING**: Unexpected exception resolving reference    
> java.sql.SQLException: The server timezone value 'UTC' is unrecognized or represents more than one timezone. You must configure either the server or JDBC driver (via the serverTimezone configuration property) to use a more specifc timezone value if you want to utilize timezone support.

Add ```serverTimezone``` argument in your database connection string,

```java
DriverManager.getConnection("jdbc:mysql://localhost:3306/dbDBdBDb?&serverTimezone=utc", "user", "Password123!");
```

or, log into MySQL server,

```sql
SET GLOBAL time_zone = '-08:00';
```

<br/>

Ref:

- [java - MySQL JDBC Driver 5.1.33 - Time Zone Issue - Stack Overflow](https://stackoverflow.com/questions/26515700/mysql-jdbc-driver-5-1-33-time-zone-issue)
- [timezone - How do I set the time zone of MySQL? - Stack Overflow](https://stackoverflow.com/questions/930900/how-do-i-set-the-time-zone-of-mysql)

Ref++:

- [MySQL :: MySQL 5.5 Reference Manual :: 5.1.12 MySQL Server Time Zone Support](https://dev.mysql.com/doc/refman/5.5/en/time-zone-support.html)
- [MySQL NOW() Function](https://www.w3schools.com/sql/func_mysql_now.asp)
- [MySQL :: MySQL 5.5 Reference Manual :: 12.7 Date and Time Functions](https://dev.mysql.com/doc/refman/5.5/en/date-and-time-functions.html)
