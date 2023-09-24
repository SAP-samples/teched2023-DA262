# Exercise 3 - Using the SQL Console
In this exercise, we will explore some of the functionality in the SAP HANA database explorer's SQL console. Please follow the examples shown below.

## Exercise 3.1 Open a SQL Console

1. A SQL console can be opened by the context menu of an instance or after selecting an instance and clicking on the SQL console toolbar icon.  

    ![](images/OpenSQLConsole.png)

    Execute the following SQL after pasting it into a newly opened SQL console that is connected to the FlightReservation HDI container and press the **Run** button.

    ```SQL
    SELECT CURRENT_USER, CURRENT_SCHEMA FROM DUMMY;
    SELECT CONNECTION_ID, START_TIME, USER_NAME, CLIENT_TYPE, CLIENT_VERSION, CLIENT_APPLICATION FROM PUBLIC.M_CONNECTIONS WHERE CONNECTION_ID = CURRENT_CONNECTION;
    ```

    Multiple SQL console tabs can be opened, or the instance that the SQL console is attached to can be changed if needed.

    ![](images/ChangeConnection.png)

## Exercise 3.2 Autocompletion

1. The SQL console can autocomplete statements.  Enter the statement below into the SQL console, position the cursor on the **C** and press **Ctrl + space**.  Select **COUNTRY** to complete the SQL query.

    ![](images/AutoComplete.png)

    ```SQL
    SELECT 	NAME, ADDRESS, C, FLDATE, SEAT
        FROM 
            PASSENGERS AS P,
            FLIGHTRESERVATION AS F
        WHERE P.PASSENGERID = F.PASSENGERID
        ORDER BY NAME ASC;
    ```

## Exercise 3.3 Statement Library

1. Commonly used statements can be saved to or retrieved from the statement library.  

    ![](images/StatementLibrary.png)

    Statements added to the statement library can viewed and opened by selecting **Show Statement Library**.  
    
    ![](images/StatementLibraryShow.png)

    In this dialog it is also possible to export selected statements or import statements from a zip file such as the diagnostic SQL statements downloaded from [SAP Note 1969700 - SQL Statement Collection for SAP HANA](https://launchpad.support.sap.com/#/notes/1969700).

## Exercise 3.4 Statement Help Panel

1. The SQL console has an optional statement help panel that shows additional details for a SQL statement that is selected by the input indicator.  Enter the statement below into the SQL console and show the Statement Help panel. 

    ![](images/StatementHelpPanel.png)
    
    *Links are provided to the SAP Help documentation as well as metadata about the tables, views procedures, or functions being used.* 

    ```SQL
    SELECT SEAT, COUNT(SEAT)
    FROM 
        PASSENGERS AS P,
        FLIGHTRESERVATION AS F
    WHERE P.PASSENGERID = F.PASSENGERID 
    GROUP BY F.SEAT
    ORDER BY F.SEAT ASC;
    ```

 ## Exercise 3.5 Messages Tab

1. Resource consumption metrics of the executed SQL statement is available in the **Messages** tab.  These provide further details into how long a query took to execute and how much memory was consumed.

    ![](images/Messages.png)

## Exercise 3.6 History Tab

1. The previously executed statements can be found in the **History** tab.  Statements can be recalled by double clicking on them or by dragging and dropping them.

    ![](images/History.png)

    >The results, messages, and history contents are not preserved following a browser reload while the SQL statements are preserved by default.

## Exercise 3.7 SQL Console Preferences

1. Examine the SQL console preferences.  Navigate to the database explorer preferences icon on the left of your screen and select **SQL Console**. Examine the available settings.  

    A few notable settings are:
    * Byte limit for the size of a returned value
    * Max number of rows to display
    * Indicate potential SQL errors can be used to enable or disable the syntax parser
    * Auto-save contents of SQL consoles
   
    ![](images/DBX_Settings.png)

    >If changes are made to this screen, the Save button must be pressed for the changes to be set.

 
 2. An example of a query that returns more than 1000 rows is shown below.  The setting Max number of rows to display could be updated to display the full result.

    ![](images/Settings.png)       

    ```SQL
    SELECT count(*) FROM TABLE_COLUMNS;
    SELECT * FROM TABLE_COLUMNS;
    ```

## Exercise 3.8 SQL Console Shortcut Keys

1.  A list of keyboard shortcuts can be found by right-clicking and selecting **Keyboard Shortcuts** within the SQL console window.

    ![](images/OpenShortcuts.png)

    ![](images/KeyboardShortcuts.png)

    Here is a list of common keyboard shortcuts for future reference:
    Action | Shortcut
    ------ | ------
    Add Comment Block | Ctrl+Shift+/
    Comment/Uncomment Line | Ctrl+/
    Format Code	|Ctrl+B
    Go to Next Error | Alt+E
    Go to Previous Error | Alt+Shift+E
    Increase/Decrease Font Size | Ctrl+Shift+Up  or Ctrl+Shift+Down
    Jump to Matching Brackets | Ctrl+Shift+M
    Run All | F8
    Run Statement |	F9
    Switch tabs	|Ctrl+Alt+Pageup  or Ctrl+Alt+Pagedown
    Text Completion | Ctrl+Space (requires two characters to be entered)

    >Note: The shortcut keys may vary depending on the browser used.

## Exercise 3.9 Additional SQL Console Tab Features 

1. A SQL console tab or a sub tab such as Results, or Messages, can enter or exit full screen mode, by double tapping on its tab.  

    ![](images/FullScreen.png)

2. A context menu is available on SQL console tabs.  You may wish to provide a more descriptive tab name for a SQL console.

    ![](images/SQLConsoleContextMenu.png)

## Exercise 3.10 Background Execution

1. Statements that may take a while to execute can be optionally run in the background.

    ```SQL
    DO BEGIN
    -- Wait for a few seconds
    USING SQLSCRIPT_SYNC AS SYNCLIB;
    CALL SYNCLIB:SLEEP_SECONDS( 5 );  --wait 5 secs
    -- Now execute a query
    SELECT * FROM PASSENGERS;
    END;
    ```

    ![](images/RunInBackground.png)

    A benefit of running a statement in the background is that the result can be examined later even from another laptop.

    ![](images/ViewBackgroundResults.png)  
  
2. Once the status has changed to SUCCESS, the results can be viewed.
    
    >Optionally press the refresh button to update the status sooner.

    >Notice that the original SQL console and the one opened to view the results are both in a disconnected state and would need to be re-connected before executing another statement.

    ![](images/ViewBackgroundResults2.png)

## Exercise 3.11 Run on Multiple Databases

1. SQL statements can also be executed against multiple databases.  Paste in the below SQL into the SQL console and from the **Run** icon select **Run on Multiple Databases**. 

    ```SQL
    SELECT CURRENT_USER FROM DUMMY;
    ```

    ![](images/RunOnMultipleDatabases.png)

    Select two or more databases.

    ![](images/RunOnMultipleDatabases2.png)

    Once the query completes, select the queries whose results should be provided into a downloadable JSON file.

    ![](images/RunOnMultipleDatabases4.png)

    An example of the results file is shown below.

    ![](images/RunOnMultipleDatabases3.png)

## Exercise 3.12 Export and Import

1. The results of a SQL query can be saved as a CSV file.  Select the Download icon.

    ![](images/Download.png)

    Options are provided on how to format the data.

    ![](images/Download2.png)

    Wizards are also provided that can be used to export the data from a table, view or from multiple objects and include their schema and data (catalog import/export).

    ![](images/ExportandImportWizards.png)

    Further details on how to configure the SAP HANA database explorer to be used with cloud storage providers can be found at [Export and Import Data and Schema with SAP HANA Database Explorer](https://developers.sap.com/tutorials/hana-dbx-export-import.html).

## Exercise 3.13 Data Viewers

1. The SQL console has built in viewers for data of different formats such as HTML, XML, JSON and spatial.  Execute the below SQL, select a value from the results tab and choose **View data**. 

    ```SQL
    SELECT'{ "name":"John", "age":30, "cars": { "car1":"Ford", "car2":"BMW", "car3":"Fiat" }}'
        AS JSON_EXAMPLE FROM DUMMY;
    
    SELECT '<?xml version="1.0" encoding="UTF-8"?>
        <breakfast_menu>
            <food>
                <name>Belgian Waffles</name>
                <price>$5.95</price>
                <description>
            Two of our famous Belgian Waffles with plenty of real maple syrup
            </description>
                <calories>650</calories>
            </food>
            <food>
                <name>French Toast</name>
                <price>$4.50</price>
                <description>
                Thick slices made from our homemade sourdough bread
                </description>
                <calories>600</calories>
            </food>
        </breakfast_menu>' XML_EXAMPLE FROM DUMMY;

    SELECT NEW ST_Point('POINT (-80.55100416451384 43.48025646678657)', 4326) FROM DUMMY;
    ```

    ![](images/view-map.png)
    
    Further details on how the SAP HANA database explorer can be used with multi-model features including graph, JSON, and spatial can be found at [Try Out Multi-Model Functionality with the SAP HANA Database Explorer](https://developers.sap.com/tutorials/hana-dbx-multi-model.html).

This concludes the exercise on the using SQL console.  Optionally, view additional content in [Appendix 1 - SAP HANA Database Explorer Extension](../ex4/README.md).

Continue to - [SAP HANA Cockpit - Exercise 1 - The Database Overview Page](../../hana_cockpit/ex1/README.md)
