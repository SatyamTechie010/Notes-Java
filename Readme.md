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


# Swing Java Program Template

```java
import javax.swing.*;
import java.awt.*;
import java.awt.event.*;

public class ProgramName implements ActionListener {

    // ================================
    // STEP 1: Declare the JFrame
    // Main window of the application.
    // ================================
    JFrame frame;

    // ================================
    // STEP 2: Declare GUI Components
    // Example:
    // JLabel label;
    // JTextField textField;
    // JButton button;
    // JCheckBox checkBox;
    // JComboBox<String> comboBox;
    // ================================

    ProgramName() {

        // ================================
        // STEP 3: Create JFrame
        // ================================
        frame = new JFrame("Title");

        // Set window size
        frame.setSize(400, 300);

        // Use Absolute Layout
        frame.setLayout(null);

        // Close application when window closes
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // ===================================================
        // STEP 4: Create Components
        // Example:
        //
        // label = new JLabel("Enter Name");
        // textField = new JTextField();
        // button = new JButton("Submit");
        //
        // ===================================================

        // ===================================================
        // STEP 5: Set Component Positions
        // Syntax:
        // component.setBounds(x, y, width, height);
        // ===================================================

        // ===================================================
        // STEP 6: Add Components to Frame
        // Example:
        // frame.add(label);
        // frame.add(textField);
        // frame.add(button);
        // ===================================================

        // ===================================================
        // STEP 7: Register Event Listeners
        // Example:
        // button.addActionListener(this);
        // ===================================================

        // ===================================================
        // STEP 8: Display the Window
        // ===================================================
        frame.setVisible(true);
    }

    // ===================================================
    // STEP 9: Handle Button Clicks and Events
    // ===================================================
    @Override
    public void actionPerformed(ActionEvent e) {

        // Example:
        // if(e.getSource() == button){
        //     // Write your logic here
        // }
    }

    // ===================================================
    // STEP 10: Program Execution Starts Here
    // ===================================================
    public static void main(String[] args) {

        // Create object to launch GUI
        new ProgramName();
    }
}
```
