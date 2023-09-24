# Appendix 1 - SAP HANA Database Explorer Extension

  In this exercise, we will examine how the SAP HANA database explorer extension can be used to browse schema and execute queries.  The extension has  a subset of the functionality available in the SAP HANA database explorer that has been shown previously.  The extension is automatically included when the development workspace is created as shown below.

  ![](images/included-extensions.png)

## Exercise 1.1 Connections

1. Select the **SAP HANA database explorer** extension.  The list of connections should appear.  This list is managed by the full SAP HANA database explorer web application and uses the currently connected cloud foundry user and org to retrieve the connection details.

    ![](images/connections.png)


## Exercise 1.2 Catalog Browser

1. Select **Tables** on the HDI Container and see that the list of deployed tables can be seen.

    ![](images/tables.png)

2. Select **Views** on the **DEMO_HANA_DB** instance.  Notice that no views are shown.  A filter is applied by default to only show views created by the connected user which is DBADMIN in this case.  

    ![](images/views-empty.png)

    Select the filter icon to set the schema to **_SYS_DI**.  
     
    Now the views that belong to the schema _SYS_DI appear.

    ![](images/views.png)

## Exercise 1.3 SQL Console

1. Select the HDI Container and open a SQL console.  Execute the below SQL.

    ![](images/sql-console.png)

    ```SQL
    SELECT NAME, CARRID, FLDATE, SEAT 
        FROM FLIGHTRESERVATION, PASSENGERS 
        WHERE PASSENGERS.PASSENGERID = 2 
        AND FLIGHTRESERVATION.PASSENGERID = PASSENGERS.PASSENGERID;    
    ```

    Notice that the result is shown and includes the Messages and History tabs.


This concludes the appendix on the SAP HANA Database Explorer extension.  Note that it is also available as a plugin for [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=SAPSE.hana-database-explorer&ssr=false#overview).    

Back to - [DA261 - SAP HANA Cloud Database Administration and Development](../../../README.md)
