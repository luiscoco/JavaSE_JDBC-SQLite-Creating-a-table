# JavaSE_JDBC-SQLite-Creating-a-table
  
1. Download the jar file "sqlite-jdbc JAR 3.15.1": https://jar-download.com/artifacts/org.xerial/sqlite-jdbc/3.15.1/source-code

2. Open the application in IngelliJ.

3. Set the the jar file "sqlite-jdbc JAR 3.15.1" path in the IntelliJ File->Project structure->Libraries:

![image](https://github.com/luiscoco/JavaSE_JDBC-SQLite-Creating-a-table/assets/32194879/70ec6efd-9e02-47af-8cc3-e27156b5022d)

![image](https://github.com/luiscoco/JavaSE_JDBC-SQLite-Creating-a-table/assets/32194879/e5ba2fba-6862-4cdb-b156-f7878179323a)

4. We have to set the Java database connection string in the Java code:

Thi is an example for the connection string:

```
Connection conn = DriverManager.getConnection("jdbc:sqlite:C:\\Java SE Luxoft training\\Java17MasterClassUdemyTraining\\section20\\Databases-Creating-Databases-With-JDBC-in-Java-Source-code\\testjava.db");
```

## Application source code

This is the whole application source code: 

```java
package com.timbuchalka;

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.SQLException;
import java.sql.Statement;

public class Main {

    public static void main(String[] args) {

//        try(Connection conn = DriverManager.getConnection("jdbc:sqlite:/Volumes/Production/Courses/Programs/JavaPrograms/TestDB/testjava.db");
//            Statement statement = conn.createStatement()) {
//            statement.execute("CREATE TABLE contacts (name TEXT, phone INTEGER, email TEXT)");
        try {
            Connection conn = DriverManager.getConnection("jdbc:sqlite:C:\\Java SE Luxoft training\\Java17MasterClassUdemyTraining\\section20\\Databases-Creating-Databases-With-JDBC-in-Java-Source-code\\testjava.db");
            //Connection conn = DriverManager.getConnection("jdbc:sqlite:/Volumes/Production/Courses/Programs/JavaPrograms/TestDB/testjava.db");
            Statement statement = conn.createStatement();
            statement.execute("CREATE TABLE contactsluis (name TEXT, phone INTEGER, email TEXT)");

            statement.close();
            conn.close();

//            Connection conn = DriverManager.getConnection("jdbc:sqlite:D:\\databases\\testjava.db");
//            Class.forName("org.sql.JDBC");

        } catch (SQLException e) {
            System.out.println("Something went wrong: " + e.getMessage());
        }
    }
}
```
