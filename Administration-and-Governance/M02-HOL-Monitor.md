# Lab 2: Reporting and Telemetry

### Estimated Duration: 90 Minutes

## Overview

In this lab, you will learn about the **monitoring capabilities of the Power Platform**. Monitoring is a critical aspect of administration and governance, as it allows you to track usage, identify potential issues, and ensure that your Power Platform environment is running smoothly.

## Objectives

In this lab, you will complete the following exercises:

- Exercise 1 - Explore the out-of-the-box analytics
- Exercise 2 – Configure Dataverse logging for a table
- Exercise 3 - Set up inventory components

<!--
### Lab Test Environment

This lab is designed to be completed in an environment set up for multiple students to complete the Admin in a day series of hands-on labs.

You need to use the assigned user and environment information to complete this lab. You must have completed the prior labs to complete this lab.
-->

## Exercise 1: Explore the out-of-the-box analytics

In this exercise, you will explore the out-of-the-box analytics that are available from the Power Platform admin center.

1. Navigate to **Power Platform admin center** page.

2. Select **Monitor (1)** from the left pane, then select **Power Apps (2)** and click on the **Open settings (3)**

    ![](images/img-01-31.png)

3. **Enable (1)** the Tenant-level analytics  and click on **Save (2)**. Navigate back to Monitor and select the Power Apps

   ![](images/img-01-32.png)

   >**Note**: Once enabled, this feature aggregates data from environments across all regions in your tenant and copies it into the default environment region for tenant-level reporting. A tenant-level administrator role is required for the one-time operation of granting consent for tenant-level analytics.

4. The **Overview** tab displays a message indicating that tenant-level analytics has been enabled. **Typically, these reports are displayed within 24-48 hours of enabling the feature**.

   ![](images/ppap.png)

    > **Note**: **The below **tasks 1,2 and 3** has been made as read-only because the service can take 24 to 36 hours to reflect service activities from the previous day**. Please go through the provided link for more details [Tenant-level analytics for Power Apps](https://learn.microsoft.com/en-us/power-platform/admin/tenant-level-analytics?tabs=new#how-do-i-enable-tenant-level-analytics)   

### Task 1: Explore the Power Automate analytics (Read only)

1. Navigate to **Power Platform admin center**.

1. From the **Manage (1)** section, and select **Power Automate (2)**. Go to **Environment view (3)** tab and click on **Change filters (4)**.

   ![](images/M02/E1T1S2-1105.png)

1. Change the Environmnent to **Power Platform COE (1)** environment and the **Apply (2)**.

   ![](images/M02/E1T1S3.1-1105.png)

1. Review the visuals in the **Runs** tab and then select the **Usage** tab.

   ![](images/M02/M2-EX1-T1-S6.png)

1. Review the visuals in the **Usage** tab.

1. Review the visuals in the rest of the tabs.

1. In the top left corner of the screen, under the header, select **Overview** to review tenant-level
    analytics.

    ![](images/M02/M2-EX1-T1-S9.png)

1. Now you are looking at data for all environments you have access to.

1. Review the **Usage** data available on this tab, and then switch to **Maker Activity** and **Inventory** to review the other data available. Notice you can still filter on more specific criteria using the dropdowns.

    ![](images/M02/M2-EX1-T1-S11.png)

### Task 2: Explore the Power Apps analytics (Read only)

1. In the **Power Platform admin center**. From **Manage (1)** section, select **Power Apps (1)**. Click on **Reports (3)** tab and change the Primary Tab to **Environment View (4)**. Click on **Change filters (5)**. Switch the environment to **Power Platform COE (6)** by changing the available filters and clicking on **Apply (7)**

   ![](images/M02/E1T2S1.1-1105.png)

   ![](images/M02/E1T2S1.2-1105.png)

1. Review the visuals in **Usage**, and all other tabs.

1. In the top left corner of the screen, under the header, select **Overview** to review tenant-level analytics.

   ![](images/M02/M2-EX1-T2-S6.png)

1. Now you are looking at data for all environments you have access to.

1. Review the **Usage** data available on this tab, and then switch to **Maker Activity** and **Inventory** to review the other data available. Notice you can still filter on more 
   specific criteria.

   ![](images/M02/M2-EX1-T2-S8.png)

1. Hover your mouse over the far-right corner of the unique user's data, and under **Region**, you can select **...** to show more options.

   ![](images/M02/M2-EX1-T2-S9.png)

1. Select **Export data**.

    ![](images/M02/M2-EX1-T2-S10.png)

1. If you have Excel installed, choose one of the options and select **Export**. After the file downloads, review the details available. If you don’t have Excel, simply select **Cancel**.

    ![](images/M02/M2-EX1-T2-S11.png)

### Task 3: Explore the Capacity analytics (Read only)

1. Navigate to **Power Platform admin center**.

1. Go to **Licensing (1)** tab and select **Capacity add-ons (2)**

    ![](images/M02/E1T3S2-1105.png)

1. Notice the data in the **Storage capacity usage** panel.

   ![](images/M02/M2-EX1-T3-S3.png)

1. Notice the data under the **Storage capacity by source** panel.

   ![](images/M02/M2-EX1-T3-S4.png)

1. Go to the **Top storage usage by environment** panel and notice the capacity usage by top environments.

   ![](images/M02/M2-EX1-T3-S5.png)

1. Select the **Dataverse** tab from the top row of options.

   ![](images/M02/M2-EX1-T3-S6.png)

1. Locate the **Device Ordering Development** environment storage capacity and select **Details**.

   ![](images/M02/M2-EX1-T3-S7.png)

1. Select the **Chart menu** button at the top right of the first chart and select **Download all tables**.

   ![](images/M02/M2-EX1-T3-S8.png)

1. Open the file that was downloaded as a result.

   ![](images/M02/pp126.png)

1. You should see a list of all tables and their database size in MB.

   ![](images/M02/M2-EX1-T3-S9.png)

1. Close the Excel file. You won’t need to save any changes you’ve made.

1. Go to the navigation pane from the **Manage (1)** tab, go to **Dataverse (2)**. Select **Home (3)** and click on **Change filters (4)**.

    ![](images/M02/E1T3S12.1-1105.png)

14. Change the **From** date to one week prior today’s date **(1)** and the **To** date to today **(2)**. Select **Apply (3)**.

    ![](images/M02/E1T3S13.1-1105.png)

15. The visuals should change to reflect your changes.

    ![](images/M02/M2-EX1-T3-S15.png)


## Exercise 2: Configure Dataverse logging for a table

In this exercise, you will configure auditing for a table in Dataverse, which is the underlying data platform for Power Apps. Auditing allows you to track changes to data in your tables, including who made the change and when it was made. This can be useful for monitoring and troubleshooting issues in your applications.

### Task 1: Review audit logging in the environment

In this task, you will enable auditing for the Project table and its Due Date column, publish customizations, and turn on auditing at the environment level.

1. Navigate to the **Power Apps** portal, and ensure that the **My Sandbox-<inject key="Deployment ID" enableCopy="false" />** environment is selected.

1. On the left navigation menu, select **Solutions (1)** and open the **Fabrikam Project Management (2)** solution.

   ![](images/M02/E2T1S2-0605.png)

1. Expand **Tables (1)** and select the **Project (2)** table. Select **Columns (3)** under the **Schema** section.

   ![](images/M02/E2T1S3-0605.png)

1. Click on the **Due Date (1)** column to open it. On the Edit column pane, expand **Advance Options (2)**.

   ![](images/M02/E2T1S4-0605.png)

1. Under the **Advanced Options** section, ensure that **Enable Auditing (1)** is enabled for this column. A notice will be underneath the option, informing you that auditing is not enabled for the organization. We will fix this in a later step. Select **Cancel (2)** to close the field details pane.

   ![](images/M02/E2T1S5-0605.png)

1. Navigate back to the Tables by selecting the **Tables** using the breadcrumbs at the top.

   ![](images/M02/E2T1S6-0605.png)

1. Select the **Project (1)** table radio button, and then select **Properties (2)** from the ribbon up top.

   ![](images/M02/E2T1S7-0605.png)

1. Expand the **Advanced options** section.

    ![](images/M02/M2-EX2-T1-S10.png)

1. Scroll down to the **For this table** section and select the **Audit changes to its data (1)** checkbox and select **Save (2)**.

    ![](images/M02/E2T1S9-0605.png)

1. Select **All (1)** from the left navigation of the solution and click on **Publish all customizations (2)** from the ribbon at the top. Wait for the publishing to be completed before moving to the next step.

    ![](images/M02/E2T1S10-0605.png)

1. Navigate to **Power Platform admin center** and select **Manage (1)**, click on **Environments (2)**, select the **My Sandbox-<inject key="Deployment ID" enableCopy="false" /> (3)** environment and click on **Settings (4)** from the ribbon at the top.

    ![](images/sand.png)

1. Expand **Audit and logs (1)** section and select **Audit settings (2)**.

    ![](images/audit.png)

1. Check on **Start Auditing (1)** checkbox, select **Save (2)**.

    ![](images/img-01-33.png)

### Task 2: Test auditing

In this task, you will open the Project Admin app, create or edit the Annual Conference project, change its Due Date multiple times, and verify the changes in Audit History.

1. Navigate back to the **Power Apps** portal where your **Fabrikam Project Management** solution is open.

1. Select **Apps (1)** and select the **Project Admin (2)** application to launch.

   ![](images/M02/E2T2S2-0605.png)

    > **Note:** If prompted to sign in, click on Sign in and provide your ODL account credentials.

1. If you can see the **Annual Conference** project, select it to open it and skip to step 5, if you do not see it, continue with the steps below.

   ![](images/M02/E2T2S3-0605.png)

   - Create a new project by selecting the green **+ New** from the ribbon at the top.

     ![](images/M02/E2T2S3.1-0605.png)

   - For the **Title**, enter **Annual Conference (1)**. Choose the **Due date** as today’s date **(2)**.

   - Then, select **Save & Close (3)**.

     ![](images/M02/E2T2S3.2-0605.png)

1. From this screen, reopen the **Annual Conference** project.

1. Change the **Due Date (1)** to any date in the future date and select **Save (2)**.

   ![](images/M02/E2T2S5-0605.png)

1. Change the **Due Date** and save a couple more times.

1. Select **Related (1)** and select **Audit History (2)**.

    ![](images/M02/E2T2S7-0605.png)

1. You should see the change history for each of your changes. Select **Update/Create** to open one of the change history records.

    ![](images/M02/pp136.png)

     >**Note**: Sometimes it might take some time to generate the Audit history, no need to wait, you can check this later. Please proceed with the next Exercise.

1. You should see the **Filed Name**, **Old Value** and **New Value**.

1. Select **Close** to close the update record.

    ![](images/M02/pp137.png)

## Exercise 3: Set up inventory components

In this exercise, you will set up the inventory components of the CoE Starter Kit. The inventory centralizes data on apps, flows, and makers, helping you monitor and manage your Power Platform environment. It enables admin apps, dashboards, and tools like DLP Editor and Set App Permissions for better governance.

### Task 1:  Import the Creator Kit and make connections

In this task, you will install the Creator Kit from AppSource, configure the HTTP with Microsoft Entra ID connection, and import the CoE Starter Kit core and governance solutions into the Power Platform COE environment.

### Task 1.1: Installation of Creator Kit

1. On the **Power Apps** portal, select the **Environment** and select **Power Platform COE**.

    ![](images/img-01-34.png)

1. Open a new tab and download the **Creator Kit** using the following link.

    ```
    https://aka.ms/creatorkitdownload 
    ```

1. You can see the downloaded file in the top right corner, **download (1)** section. Click on the **Folder (2)** icon to open the folder in the File Explorer.

   ![](images/img-01-110.png)

1. Navigate back to the **Power Apps** portal and, from the left navigation menu, select **Solutions (1)**. On the **Solutions** page, select **Import solution (2)**.

    ![](images/img-01-111.png)

1. On the **Import a solution** page, select **Browse**, and choose the file that you downloaded.

    ![](images/M02/E3T1S5-0605.png)

    ![](images/img-01-113.png)

1. After selecting the file, on the **Import a solution** page, click **Next**. Select **Import**.

    ![](images/M02/E3T1S6.1-0605.png)

    ![](images/M02/E3T1S6.2-0605.png)

1. Wait for the import to complete, and then proceed with the next steps.

### Task 1.2: Create Connections

1. Open a new tab and navigate to the **Power Automate** portal by using the following URL.

    ```
    https://make.powerautomate.com/
    ```

1. Click on thr **Environments (1)** and select **Power Platform COE (2)**.

    ![](images/M02/E3T1.2S2-0605.png)

1. Select **More (1)** from left navigation and click on **Connections (2)** 

    ![](images/M02/E3T1.2S3-0605.png)

1. Select **+ New Connection**.

    ![](images/M02/E3T1.2S4-0605.png)

1. Search for **HTTP with Microsoft Entra ID (1)** and then click on **+ (plus sign)** sign on **HTTP with Microsoft Entra ID (preauthorized) (2)**

    ![](images/M02/E3T1.2S5-0605.png)

1. Set the **Base Resource URL (1)** and **Microsoft Entra ID Resource URI (Application ID URI) (2)** to https://graph.microsoft.com/. Click **Create (3)**.

    ![](images/img-01-37.png)

    > **Note:** On the **Pick an account** pop-up, select <inject key="AzureAdUserEmail"></inject>.

1. On the **Confirmation required** page, select the check-box of the **I have verified this request and trust the source (1)**, and select **Allow access (2)**.

    ![](images/img-01-38.png)

### Task 1.3: Import the core components solution

1. Open a new tab in the browser, copy and paste the URL below to download the **CoE Starter Kit** to your virtual machine.

    ```
    https://aka.ms/CoeStarterKitDownload
    ```

1. You can see the downloaded file in the top right corner, **download (1)** section. Click on the **Folder (2)** icon to open the folder in the File Explorer.

    ![](images/M02/pv11.png)

1. Locate the downloaded **CoEStarterKit.zip** file.

1. Right-click on the **ZIP file (1)** and select **Extract All... (2)**.

    ![](images/M02/pv12.png)

1. In the dialog box that appears, review the **destination path (1)** and then click on the **Extract (2)** button to unzip the contents.

    ![](images/M02/pv13.png)

    > **Note:** The CoE Starter Kit compressed file contains all solution components in addition to the non–solution-aware components that make up the CoE Starter Kit. 

1. Navigate back to the [Power Apps](https://make.powerapps.com/) portal.

1. Choose the **Power Platform COE (1)** Environment. In the left menu, click **Solutions (2)**. Click the **Import solution (3)** button at the top.

    ![](images/M02/E3T1.3S7-0605.png)

1. Click **Browse**.

    ![](images/M02/E3T1S5-0605.png)

1. Navigate to  **`C:\Users\demouser\Downloads\CoEStarterKit` (1)** then select **CenterOfExcellenceCoreComponents_4.50.9_managed.zip (2)** solution file from the extracted folder then click on **Open (3)**.

    ![](images/f1.png)

1. Click **Next**.    

    ![](images/M02/E3T1.3S10-0605.png)

1. Review the details, click **Next** twice, and leave all environment variable values as default until you see the Import button.

1. Finally, click on **Import**.

    ![](images/M02/E3T1.3S12-0605.png)

14. Please wait until this is complete before moving on to new tasks. This may take **20–30 minutes**. During the import, you may see a **warning notification** at the top of the screen (e.g., "Flow imported with warnings"). This is expected and does not necessarily indicate a failure.

    > **Note**: You can proceed to the next Lab or page. Once this installation is completed, please complete this remaining exercise.

    ![](images/M02/E3T1.3S13-0605.png)

1. After 20-30 minutes, please do refresh the portal, and then you will be able to see the successfully imported message.

### Task 1.4: Install COE Governance Solution.

1. From the Solutions tab, click on the **Import solution** button at the top.

1. Click on **Browse (1)**.

1. Navigate to `C:\Users\demouser\Downloads\CoEStarterKit` (2) folder then select the following file **CenterofExcellenceAuditComponents_3.27.7_managed.zip (3)** and then click on **Open (4)**.

    ![](images/f2.png)

1. Review the details, click **Next** three times, and leave all environment variable values as default until you see the Import button.

1. Finally, click on **Import**.

    ![](images/M02/E3T1.4S5-0605.png)

1. Wait for the import process to complete. This may take **5 minutes**. During the import, you may see a **warning notification** at the top of the screen (e.g., "Flow imported with warnings"). This is expected and does not necessarily indicate a failure.

1. Please do **Refresh** the portal after 5-7 minutes, then you will be able to see the successfully imported message.

    ![](images/M02/E3T1.4S7-0605.png)

1. Once the import is complete, in the Solutions page, select **All (1)** and then you can verify the installation by checking the **Center of Excellence – Core Components and Center of Excellence - Governance Components (2)**.

    ![](images/M02/E3T1.4S8-0605.png)

### Task 2: Set up the Inventory components using the Setup Wizard

In this task, you will launch the CoE Setup and Upgrade Wizard, configure environment variables and personas, run setup and inventory flows, and complete the setup to enable inventory dashboards and apps.

1. From the Solution page, navigate to **Managed (1)** and open the **Center of Excellence - Core Components (2)** solution.

    ![](images/M02/E3T2S1-0605.png)

1. Navigate to **Apps (1)** then click on the ellipse in **COE Admin Command Center (2)** app and then **Play (3)**.

    ![](images/M02/E3T2S2-0605.png)

1. On the Allow CoE Admin Command Center, to access your data? window, click **Sign In (1)** for RSS, then click **Allow (2)**. 

    ![](images/M02/E3T2S3-0605.png)

1. Click **Environment Varibles (1)** under **CoE configuration** from left navigation pannel and then click **admin_AdminMail (2)**, then click **edit (3)**.

    ![](images/M02/pv21.png)

1. On the **Configure Environment Variable** window, paste **<inject key="AzureAdUserEmail"></inject> (1)** email id in the **Value** section , then click **Save (2)**

    ![](images/M02/E3T2S5-0605.png)

1. Now return to the previous tab where your **Center of Excellence - Core Components** solution is open.

    ![](images/M02/ppm8.png)

1. Open the CoE Setup and Upgrade Wizard app. Click **Apps** **(1)**, Click the three ellipses (⋯) next to the **CoE Setup and Upgrade Wizard** **(2)**. Select **Play** **(3)** to launch the app.

    ![](images/M02/pv22.png)

1. Grant all app permissions and click **Allow**.

    ![](images/M02/E3T2S8-0605.png)

1. Confirm pre-requisites: Click **Next**.

    ![](images/M02/pv23.png)

1. Configure communication methods: Click **Configure group (1)** and select **Create new group (2)** under Admin persona.

    ![](images/M02/E3T2S10-0605.png)

1. You will be navigated to the Azure portal. Select **Microsoft 365** **(1)** for group type. Give group name as **COE Admin Group** **(2)**. Click **No Owners Selected** **(3)**. 

    ![](images/M02/E3T2S11-0605.png)

1. Search for **odl (1)**, select the **environment email ID (2)**, and then **Select (3)**. Similarly, you can select multiple members to assign to the Admin persona. 

    ![](images/M02/E3T2S12-0605.png)

1. Once you've made your selections, click **Create** to proceed.    

1. Navigate back to the **CoE Setup and Upgrade Wizard** tab. **Refresh** the page, then proceed to configure the Admin persona by selecting the newly created group **COE Admin Group (1)** and then **Select group (2)**.

    ![](images/M02/E3T2S14-0605.png)

1. In the same way, you can create new groups for the **Maker persona** and **User persona**. For now, you can select the same **CoE Admin Group** for both **(1)**.

1. After completing all three configurations, click **Next (2)** to continue.

    ![](images/M02/E3T2S16-0605.png)

1. **Configure mandatory settings**: Review tenant ID from Service principal details in the environment section of the lab guide and select **Next**

1. **Configure inventory data source** : Click **Next**.

    ![](images/M02/pv30.png)

1. **Run setup flows**: Click **Refresh (1)**, wait about 5 minutes for the process to complete **(2)**, then refresh again. Once done, click **Next (3)**.

    ![](images/M02/E3T2S19.1-0605.png)

    ![](images/M02/E3T2S19.2-0605.png)

1. **Run Inventory flows**: Click the toggle button for all the flows available on the page, wait until all the flows are removed from the page, and then click **Next**.

    > **Note**: This page might take 1-2 hours sometimes to load. Proceed with further modules and keep this run in the background.

    ![](images/M02/pv31.png)

1. **Configure dataflows**: Click **Next**.

1. **Share apps**: Click **Next**.

1. Publish PowerBI dashboard: Click **Next** and then **Done**

1. Close **CoE Setup and Upgrade Wizard** application.

    > **Note:** For additional details about the Center of Excellence (CoE), we recommend reviewing the Microsoft Learn overview:
    > https://learn.microsoft.com/en-us/power-platform/guidance/coe/overview

## Summary

In this lab, you have accomplished the following:

- Exercise 1 - Explored the out-of-the-box analytics
- Exercise 2 – Configured Dataverse logging for a table
- Exercise 3 - Set up inventory components

### You have successfully completed this module. Click **Next** from the lower right corner to move on to the next page.

![Launch Azure Portal](images/gp8.png)

