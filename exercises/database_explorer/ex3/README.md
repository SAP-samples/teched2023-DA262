# Exercise 3 - Using the SQL Console
This exercise will explore some of the functionality in the SAP HANA database explorer's SQL console that is unique to the SQL Console in the SAP HANA database explorer.  Please follow the examples shown below.

## Exercise 3.1 Autocompletion
The SQL console offers to autocomplete statements.  

1. Enter the statement below into the SQL console, position the cursor on the **C** and press **Ctrl + space**.  Select **CUSTOMER_NAME** to complete the SQL query.

    ![](images/AutoComplete.png)

    ```SQL
    SELECT HOTEL_NAME, ARRIVAL, FIRSTNAME, C 
        FROM HOTEL.RESERVATION_VIEW;
    ```

## Exercise 3.2 Statement Library
Commonly used statements can be saved to or retrieved from the statement library.  

1. Execute the following query and then save it to the statement library by pressing the **Add to Statement Library** icon.

    ```SQL
    SELECT HOTEL_NAME, ARRIVAL, FIRSTNAME, CUSTOMER_NAME 
        FROM HOTEL.RESERVATION_VIEW 
        WHERE ARRIVAL > CURRENT_DATE
        ORDER BY ARRIVAL ASC;
    ```

    ![](images/StatementLibrary.png)

    A description is optional.

    ![](images/StatementLibraryAdd.png)

2. Statements added to the statement library can viewed and opened by selecting **Show Statement Library**.  

    ![](images/StatementLibraryShow1.png)

    
    ![](images/StatementLibraryShow2.png)

    In this dialog it is also possible to export selected statements or import statements from a zip file such as the diagnostic SQL statements downloaded from [SAP Note 1969700 - SQL Statement Collection for SAP HANA](https://launchpad.support.sap.com/#/notes/1969700).

 ## Exercise 3.3 SQL Console Preferences

1. Examine the SQL console preferences.  Navigate to the preferences icon on the left of your screen and select **SQL Console**. Examine the available settings.  

    A few notable settings are:
    * Byte limit for Large Objects
    * Max number of rows to display
    * Indicate potential SQL errors can be used to enable or disable the syntax parser
    * Auto-save contents of SQL consoles
   
    ![](images/DBX_Settings.png)

    >If changes are made to this screen, the Save button must be pressed for the changes to be set.

 
 2. Execute the SQL below.

    ![](images/Settings.png)       

    ```SQL
    SELECT count(*) FROM TABLE_COLUMNS;
    SELECT * FROM TABLE_COLUMNS;
    ```

    This query returns more than 6000 rows but only the first 1000 rows are shown.  Setting Max number of rows to a higher limit will enable more rows to be displayed.


## Exercise 3.4 SQL Console Shortcut Keys

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
    Go to Line | Ctrl+L
    Increase/Decrease Font Size | Ctrl+Shift+Up  or Ctrl+Shift+Down
    Jump to Matching Brackets | Ctrl+P
    Run All | F8
    Run Statement |	F9
    Switch tabs	|Ctrl+Alt+Pageup  or Ctrl+Alt+Pagedown
    Text Completion | Ctrl+Space (requires two characters to be entered)

    >The shortcut keys may vary depending on the browser used.

## Exercise 3.5 Additional SQL Console Tab Features 
A SQL console tab or a sub tab such as Results, or Messages, can enter or exit full screen mode, by double clicking on its tab.  

1. Double click on the tabs indicated below. 

    ![](images/FullScreen.png)

2. A context menu is available on SQL console tabs.  Rename the tab indicated below to a more descriptive tab name.

    ![](images/SQLConsoleContextMenu.png)

## Exercise 3.6 Background Execution
Statements that may take a while to execute can be optionally run in the background.

1. Execute the below SQL in the background.

    ```SQL
    DO BEGIN
    -- Wait for a few seconds
    USING SQLSCRIPT_SYNC AS SYNCLIB;
    CALL SYNCLIB:SLEEP_SECONDS( 5 );  --wait 5 secs
    -- Now execute a query
    SELECT * FROM HOTEL.HOTEL;
    END;
    ```

    ![](images/RunInBackground.png)

    A benefit of running a statement in the background is that the result can be examined later even from another laptop.

    ![](images/ViewBackgroundResults.png)  
  
2. Once the status has changed to SUCCESS, the results can be viewed.
    
    >Optionally press the refresh button to update the status sooner.

    >Notice that the original SQL console and the one opened to view the results are both in a disconnected state and would need to be re-connected before executing another statement.

    ![](images/ViewBackgroundResults2.png)

## Exercise 3.7 Run on Multiple Databases
SQL statements can also be executed against multiple databases.  

1. Execute the SQL below using the **Run** icon with the option **Run on Multiple Databases**. 

    ```SQL
    SELECT * FROM M_HOST_INFORMATION 
        WHERE KEY = 'build_qrc_version';
    ```

    ![](images/RunOnMultipleDatabases.png)

    Select one or more databases.

    ![](images/RunOnMultipleDatabases2.png)

    Once the query completes, select the queries whose results should be provided into a downloadable JSON file.

    ![](images/RunOnMultipleDatabases4.png)

    An example of the results file is shown below.  If multiple databases were selected, there would be multiple results shown in the JSON file.

    ![](images/RunOnMultipleDatabases3.png)

## Exercise 3.8 Import and Export

1.  Wizards are provided that can be used to import data or to export the data from a table, view or from multiple objects and include their schema and data (catalog import/export).

    ![](images/ExportandImportWizards.png)

    Further details on how to configure the SAP HANA database explorer to be used with cloud storage providers can be found at [Export and Import Data and Schema with SAP HANA Database Explorer](https://developers.sap.com/tutorials/hana-dbx-export-import.html).

## Exercise 3.9 Data Viewers
An additional data viewer supported by the SQL Console in the SAP HANA database explorer is a spatial viewer.  

1. Execute the below SQL.

    ```SQL
    SELECT NAME, ADDRESS, CITY, STATE, LOCATION 
        FROM HOTEL.HOTEL;
    ```

2. Select one or more location values and choose  **View spatial data**. 

    ![](images/view-map.png)

    A marker is shown for each location and includes details from the table.

    ![](images/view-map2.png)
    
    Further details on how the SAP HANA database explorer can be used with multi-model features including graph, JSON, and spatial can be found at [Try Out Multi-Model Functionality with the SAP HANA Database Explorer](https://developers.sap.com/tutorials/hana-dbx-multi-model.html).

This concludes the exercise on the using SQL console.  Optionally, view additional content in [Appendix 1 - SAP HANA Database Explorer Extension](../ex4/README.md).

Optionally continue to - [SAP HANA Cockpit - Exercise 1 - The Database Overview Page](../../hana_cockpit/ex1/README.md)
