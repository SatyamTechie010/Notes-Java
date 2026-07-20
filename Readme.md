# JDBC PostgreSQL Connection with Comments

```java
import java.sql.*;

public class JdbcQ1 {

    public static void main(String[] args) {

        try {

            // ================================
            // STEP 1: Specify the JDBC Driver
            // Trick: "Driver ko pehle load karo."
            // ================================
            String driver = "org.postgresql.Driver";

            // ================================
            // STEP 2: Database URL
            // Format:
            // jdbc:postgresql://hostname:port/database_name
            // ================================
            String url = "jdbc:postgresql://localhost:5432/mca_25_db";

            // ================================
            // STEP 3: Database Credentials
            // Used for authentication.
            // ================================
            String username = "postgres";
            String password = "25MMCE54";

            // ================================
            // STEP 4: Load the Driver
            // Makes the JDBC driver available to JVM.
            // ================================
            Class.forName(driver);

            // ================================
            // STEP 5: Establish Connection
            // DriverManager selects the correct driver
            // and returns a Connection object.
            // ================================
            Connection con = DriverManager.getConnection(url, username, password);

            // ================================
            // STEP 6: Verify Connection
            // ================================
            if (con != null) {
                System.out.println("Connected...");
            }

            // ================================
            // STEP 7: Close Connection
            // Always close resources to prevent
            // memory leaks and free database connections.
            // ================================
            con.close();

        } catch (Exception e) {

            // Handles exceptions such as:
            // • Driver not found
            // • Invalid URL
            // • Wrong username/password
            // • Database server not running
            System.out.println(e);
        }
    }
}
```