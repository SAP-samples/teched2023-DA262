# Exercise 1: Overview of SAP HANA Cloud Central

The SAP HANA Cloud Central tool is used to monitor all your SAP HANA Cloud instances and perform administrative tasks on them. With SAP HANA Cloud Central, you can monitor resource utilization (memory, CPU and disk), alerts, table usage, database services, SAP HANA native storage extensions (NSE), and database performance metrics (threads, sessions, SQL statements, workload classes and connections). You can also manage table distribution and perform security tasks such as user and role management, data encryption, auditing, data anonymization and trust configuration.

**Note:** SAP HANA Cloud Central can also be used to administer and monitor SAP HANA Cloud, data lake instances; but this workshop will focus on SAP HANA Cloud, SAP HANA database instances.

This exercise will teach you the basics of navigating the Database Overview Page and how to find the instance health information you need as a database administrator.

1. If SAP HANA Cloud Central is already opened, skip to the next step. Otherwise, open **SAP BTP Cockpit** -> Click **Instance and Subscriptions** under **Services** on the left nav bar -> CLick **Go to Application** button from SAP HANA Cloud Application
    <kbd>
    ![](./images/1.png)
    </kbd>

2. SAP HANA Cloud Central is launched in a new tab. We are using the Multi-Environment Edition for this workshop (the "old" Cloud Foundry Edition of SAP HANA Cloud Central will be discontinued). To verify that you are in the correct landscape, click the **i** (About) button in the lower left corner. 
    <kbd>
    ![](./images/2.png)
    </kbd>
* An Alternative way is to check the left navigation bar: The **Alerts** and **SQL Console** buttons are only available in Multi-Environment Edition of SAP HANA Cloud Central, and not the Cloud Foundry edition.

The SAP HANA Cloud Central tool is divided into several sections:

 * The left panel allows navigation between your SAP HANA Cloud instances and the Migrations application used to migrate SAP HANA Service databases or SAP HANA on premise databases to SAP HANA Cloud. You can also manage alerts using the Alert application, as well as open the SQL console.
 * The top panel offers different views and filters you can use to customize how your instances list is displayed, as well as providing search capability.
 * The bottom panel displays all your instances, with the option to group the list by instances and personalize the view.

As an SAP HANA Cloud administrator, you will likely spend a lot of time monitoring all your instances in SAP HANA Cloud Central. From the instances list, you'll be able to see computing details of your databases, whether they are running or stopped, review their notifications, and perform actions on them.

Continue to - [Exercise 2: Refresh and Auto-Refresh](../ex2-Refresh/README.md)

