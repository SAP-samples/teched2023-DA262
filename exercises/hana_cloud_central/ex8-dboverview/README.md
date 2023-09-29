# Exercise 8: The Databsed Overview Page

The SAP HANA Cloud Central can be used to administer data lake, but this exercise will focus on SAP HANA database. With the SAP HANA CLoud Central, you can monitor resource utilization (memory, CPU and disk), alerts, table usage, database services, SAP HANA native storage extensions (NSE), and database performance metrics (threads, sessions, SQL statements, workload classes and connections). You can also view backups, manage configuration parameters, manage table distribution, administer smart data access (SDA) and administer smart data integration (SDI). Finally, you can perform security tasks such as user and role management, data encryption, auditing, data anonymization and trust configuration.

Through the Database Overview page, you can view key health indicators for this specific database, such as database status and resource utilization. You also have access to tools that allow you to perform database administrations tasks, such as performance analysis and executing SQL statements. Different parts of a single card can link to different views or applications. This way, you can see various components in a single view and make the decision whether to further examine issues by drilling down.

This exercise will teach you the basics of navigating the Database Overview page and how to find the information you need as a database administrator.

1. Open the **SAP HANA CLoud Central** application
    <kbd>
    ![](./images/1.png)
    </kbd>
2. On the bottom panel, you'll find a list of instances. Click the right arrow on the bery right end of instance DEMO_HANA_DB to access the database overview page.
    <kbd>
    ![](./images/2.png)
    </kbd>
    Click the expand button to get full screen
    <kbd>
    ![](./images/3.png)
    </kbd>

3. Alternativly, you can use the command palette. Click the search button on the toolbar -> type "overview" -> Select "Show Overview" for DEMO_HANA_DB. It will take you to the same page as we get in step 2.
   <kbd>
    ![](./images/5.png)
    </kbd>
4. Below the toolbar you see the collapsible header, where you'll find the status of the database, the database user you're connecting as, the host name, and associated Data Lake. From the header, you can also manage configuration,open the SQL Console, and Copy SQL endpoint. 
    <kbd>
    ![](./images/4.png)
    </kbd>

    By default, when you first access the Database Overview page you see a quick synopsis of the database status, as well as the utilization of Memory, CPU, Storage and Network.
    
    As you scroll down, you see high-level performance metrics in the form of the number of threads, sessions and long-running statements. You also see general information about your SAP HANA Cloud database.
    
    Down further, you see security settings, such as User & Authorization Management. There are also a number of hyperlinks to launch additional administration applications.

#
Continue to - [Exercise 9: Monitoring Memory Usage](../ex9/README.md)
