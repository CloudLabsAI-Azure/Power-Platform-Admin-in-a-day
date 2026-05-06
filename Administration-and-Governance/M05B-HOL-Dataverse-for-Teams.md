# Lab 6: Explore the CoE Starter Kit (Optional)

### Estimated Duration: 75 Minutes

## Overview

In this lab, you will explore the Center of Excellence (CoE) Starter Kit—a powerful toolkit that helps you manage, govern, and nurture Power Platform adoption within your organization. You’ll learn how to leverage insights from the CoE dashboard, track connector usage, review audit logs, and apply compliance processes to applications.

By the end of this lab, you will gain practical experience in using the CoE Starter Kit to support effective governance and make informed decisions regarding app usage and security.

## Objectives

In this lab, you will complete the following exercises:

- Exercise 1 - Explore the CoE Starter Kit
- Exercise 2 - How much is a connector used in your
- Exercise 3 - Review tenant audit logs 
- Exercise 4 - Application Compliance Process

**Note:** This lab depend on the successful setup of the Inventory component of the CoE Starter Kit, which you completed in a previous exercise. Once the setup is complete, it may take approximately 3–4 hours for the data to be fully reflected in both the Power Platform and Power BI.

You may proceed with the exercises if the data has loaded successfully. If not, you'll need to wait until the data becomes available if the time permits or you can review the exercises to familiarize yourself with the lab content.

## Exercise 1: Explore the CoE Starter Kit

In this exercise, you will explore some of the apps and analytics that are part of the Power Platform CoE Starter Kit. We have already installed and configured the starter kit for the 
tenant you are using for this lab. As part of configuring, we imported the solution, shared the apps, configured the flows that synchronize data and published the Power BI report. If you 
were doing this with your tenant, you would follow the instructions to complete these steps.

Now in this exercise, you will explore the following key components:

- Power Platform Admin View app
- Power BI Dashboard
- The business process that is used by the Developer Compliance process.

### Task 1: Explore the Power Platform Admin View app

In this task you will, launch the Admin View app in the CoE environment to review apps, flows, environments, connectors, and makers. Explore governance features like business justification, risk assessment, and app catalog tagging.

1. Navigate to **Power Apps** and select the **Power Platform CoE** environment in the environment selector.

   ![](images/M02/pv93.png)

3. Select **Apps (1)** from the left side navigation and you should see a list of available apps in this environment, click on three dots in **Power Platform Admin View (2)**, Click **Play (3)**.

   ![](images/M02/pv94.png)

4. When the app starts you will land on the Power Platform Dashboard page. This dashboard gives you a quick look at the most active makers, and environments.

   ![](images/M02/M2-EX3-T1-S4A.png)

5. Select **PowerApps Apps** and you will see a list of all apps in all environments without having to visit each environment. The Flows navigation link does the same thing for Microsoft Power Automate flows.

   ![](images/M02/pv95.png)

6. Select the any app in the list to open the app details.

   ![](images/M06/E1T1S5-0605.png)

7. In the **Governance** tab you can see the Business Justification provided by the app maker using the Developer Compliance Center app. The bottom part is where you as an admin can provide your risk assessment. You can also tag the app to show in the App Catalog and make it featured. You can customize the CoE entities to add additional fields here if needed.

   ![](images/M06/E1T1S6-0605.png)

8. Select **Environments (1)** in the left navigation. This will show you a list of all the environments in your tenant and key metrics like several apps. To view all your environments, similar to the image below, switch the view at the top to **Active Environments (2)**.

   ![](images/M06/E1T1S7-0605.png)

9. Select any environment to open the detail form and review the data available.

11. Select the **Connectors (1)** link from the left navigation. This shows all the connectors available **(2)**.

    ![](images/M02/pv97.png)

12. In the upper right corner, search for **Microsoft Dataverse (1)**. In the search results, select the **Microsoft Dataverse (2)** connector.

    ![](images/M02/pv98.png)

13. The **Used in app (1)** tab quickly shows you what apps are using this connector in all **environments (2)** in your tenant.

    ![](images/M06/E1T1S11-0605.png)

14. Expand **Users (1)** and select **Makers (2)** from the left navigation; this shows you all the **people (3)** who have built apps in your company.

    ![](images/M02/pv101.png)

15. Select one of the Makers and explore the detail form.


### Task 2: Power BI Dashboard

In this task you will, use the environment URL, configure the Production and Governance dashboard in Power BI Desktop, connect it to Dataverse, and review reports. Publish the dashboard to your workspace to monitor tenant-wide adoption, app usage, and environment activity.

### Task 2.1: Get the environment URL

You need the URL of the Power Platform environment where the CoE Starter Kit is installed. Power BI connects to Dataverse tables in that environment.

1. Navigate to Power Platform admin center using the below URL in a new tab:

    ```
    https://aka.ms/ppac
    ```

2. Select **Manage (1)** from the left navigation pane. Then click on **Environments (2)** and select the **Power Platform CoE environment (3)** where you have installed the CoE Starter Kit.

    ![](images/M06/E1T2.1S2-0605.png)

3. Copy the URL under **Environment URL (1)** and save it in notepad for later use.

    ![](images/M06/E1T2.1S3-0605.png)

### Task 2.2: Configure the Production and Governance Power BI dashboard

1. Navigate to Power BI portal using the following URL in a new browser tab:

    ```
    https://app.powerbi.com/
    ```

1. Enter the below email and click on **Submit (2)**.

    - Email: **<inject key="AzureAdUserEmail"></inject> (1)**

    ![](images/M06/E1T2.2S2-0605.png)

1. If prompted, please solve the puzzle.    

1. On the You've selected Microsoft Fabric free page, select **Sign in**.

    ![](images/M06/E1T2.2S4-0605.png)

1. On the **Create your account** page, provide the following details and then click on **Get started (4)**.

   - Country: **Unites states (1)**
   - Job: **PowerPlatformEngineer(2)**
   - Phone number: Enter random 10 digits **(3)**

     ![](images/M06/E1T2.2S5-0605.png)

1. Click on **Get Started**.

    ![](images/M06/E1T2.2S6-0605.png)

1. Click on the **Acoount manager icon (1)** from the top right corner and then click on **Free trial (2)**.

    ![](images/M06/E1T2.2S7-0605.png)

1. On the **Activate your 60-day free fabric trail capacity** window, click on **Activate**.

    ![](images/M02/pt7.png)

1. On the **Your PowerBI Free trial has started** window, click on **Got it**.

1. On the left side navigation select **Workspaces** and then click on **+ New workspace (2)**.

    ![](images/M02/pt9.png)

1. On the Create panel, provide a unique name like **CoE-LabAdmin<inject key="Deployment ID" enableCopy="false" /> (1)** and your lab admin user number and select **Apply (2)**.

   ![](images/M06/E1T2.2S11-0605.png)

1. In Power BI portal, click on **Settings (1)** (gear box icon) from the top right corner, and select **Admin portal (2)**.

    ![](images/M06/adminportal-0605.png)

1. In the Admin portal, select **Tenant settings (1)**, search for **map (2)**. Enable the setting **Use Map and Filled Map visuals (3)** and click on **Apply (4)**.

    ![](images/M06/adminportal1-0605.png)

1. Launch **Power BI Desktop** from thr LabVM desktop.

   ![](images/M02/ppt22.png)

1. Close any popup window.

1. Click on **Sign in** from the top bar, sign-in with your lab credentials.

1. Once signed in, click on **Open (1)**, then **Browse this device (2)**.

    ![](images/M02/pt11.png)

1. Path for Report : `C:\Users\demouser\Downloads\CoEStarterKit` **(1)**. Select **Production_CoEDashboard_MMMYY.pbit** **(2)**, and then **Open (3)**. 

    ![](images/M02/pv100.png)

1. Wait for sometime you will notice popup appears for org URL.    

1. Wait for report to load. Enter the URL of your environment instance that you have copied earlier. Include the https:// prefix for OrgUrl **(1)**. Then Click **Load (2)**.

    ![](images/M02/pt11C.png)

    >**Note:** If the report loads before you provide the Environment URL,then follow below steps: 
    > - Click on **Transform Data (1)**, then select **Edit Parameters (2)**.
    > ![](images/M02/pv104.png)
    
    > - Paste your **Environment URL (1)** then tenant type as **commercial (2)** and the click **Ok (3)**.
    > ![](images/M02/pv105.png)  

    > - Click on Apply changes in the yellow banner.
    > ![](images/M06/E1T2.2S18note3-0605.png)   
    
    > - When prompted to Sign in, click on **Sign in (1)** and use lab credentials to login. Then click on **Connect (2)**.
    > ![](images/M06/E1T2.2S18note4-0605.png)

1. The report should load automatically once the refresh has been completed.

1. Follow the steps below to enable **map and filled map visuals**:

    - Click on **File** from the top left corner, then select **Options and Settings (2)** > **Options (3)**.

        ![](images/M06/E1T2.2S20.1-0605.png)
   
        ![](images/M06/E1T2.2S20.2-0605.png)
   
    - Select **Security (1)** from the left.
   
     - Scroll down to the Map and Filled Map visuals section and check the **Use Map and Filled Map visuals (2)** checkbox.
   
    - Select **OK (3)** to close the Options dialog.

        ![](images/M02/pv106.png)

1. Review the **Introduction** page.

    ![](images/M02/pv108.png)

1. Select the **Overview – Power Apps** tab, notice it gives a good high-level look at our tenant activity. If you have multiple locations, it will quickly highlight which users are more engaged with building apps. You can also quickly see which environments are most active. Additionally, items that are detailed as **(Blank)** indicate that there is no data to reference in the table.

    ![](images/M02/M2-EX3-T2-S24.png)

1. Review each page using the navigation at the bottom of the app and review the insights available.

1. Select any **Environment** visual to view the filtered datain the report

    ![](images/M02/M2-EX3-T2-S27-1.png)

1. Select **Apps**. On the **Apps** page notice the Creation Trend, this is an effective way to watch adoption progress.

    ![](images/M02/M2-EX3-T2-S29-1.png)

1. Select the other pages via the tabs at the bottom and review the data available.

1. Select **Publish** from the **Home** tab in the ribbon at the top.

    ![](images/M02/M2-EX3-T2-S31.png)

1. Save the report if prompted as **PBI Report (Your Initials)**, which will look something like **PBI** **Report HR** for example.

1. Select the **CoE-LabAdmin<inject key="Deployment ID" enableCopy="false" /> (1)** workspace you created and choose **Select (2)**.

     ![](images/M02/pt13.png)

1. Wait for the publishing to complete and then click on **Got it**.

1. Navigate to the Power BI Portal, and select **Workspaces (1)** and then **CoE-LabAdmin<inject key="Deployment ID" enableCopy="false" /> (2)** Workspace you created.

     ![](images/M02/pt14.png)

1. Select the **Production_COEDashboard** with the type of **Report** from the list. You’ll notice a few other items have been generated; these are done by default.

     ![](images/M02/pv110.png)

1. Once the report loads, select the **Environments** page. Use any filters to visualize data.

     ![](images/M02/M2-EX3-T2-S37-1.png)

1. You have now successfully deployed the Power BI reports that come with the CoE starter kit.


## Exercise 2: How much is a connector used in your Apps

In this exercise, you will explore the Power Platform Admin View app in the CoE Starter Kit to locate resources that use the Office 365 Outlook connector. You will review filtered data to evaluate apps/flows using it and their connector tier.

### Task 1: Locate resources that use the Office 365 Outlook connector

In this task you will, open the App Connector deep dive page in Power BI, select the Office 365 Outlook connector, and review filtered data to evaluate apps/flows using it and their connector tier.

1. Navigate to the **Power BI report** you just published.

2. Select the **App Connector deep dive** page in the report.

3. You can click on **Office 365 outlook** connector in visual to view the filtered data. 

   ![](images/M02/M2-EX5-T1-S3-1.png)

5. Using this you could evaluate things like the apps/flows using connector or Connector tier.


## Exercise 3: Review tenant audit logs 

In this exercise, you will review tenant audit logs in Microsoft Purview. You will search and filter the logs to find specific activities related to Power Apps and Power Automate, such as flow edits, and learn how to export the data for further analysis.

### Task 1: Review audit logging in the environment

In this task you will, open Microsoft Purview, navigate to Audit, and start recording activity. Perform a search to view logs, export data if needed, and filter results by activity type, user, or item. This allows admins to track activities such as flow edits and review detailed audit information for governance and compliance. 

1. Navigate to **Microsoft purview** using the following URL:

    ```
    https://purview.microsoft.com/
    ```

1. Click on **Get Started**.

   ![](images/M02/ppt23.png)

1. Select **Solution (1)** and then choose **Audit (2)** on the left side navigation.

   ![](images/M02/ppt24.png)

1. Click on the **Start recording user and admin activity**.

   ![](images/M02/ppt25.png)

1. On the COmplete organizational setup window, click on **Yes**.

1. Select **Search** using the default search criteria.

   ![](images/M06/E3T1S6-0506.png)

1. The **Job Status** will read as **Queued** once it has been set to process. **Refresh** the audit every few minutes or so until the status reads as **Completed**.

   ![](images/M2-EX6-T1-S5.png)

1. Select the Search name, which defaults to the audit date if no name has been inputted.

   ![](images/M2-EX6-T1-S6.png)

    >**Note**: Portal will be updating your organization to support customization. So it might take around 24 to 48 hours to show the data and activities.

     ![](images/M02/ppt26.png)    

1. Please go through the steps, no need to perform as currently there is no data available.     

1. Review the items displayed; drill into a few of them to see the type of data available.

   ![](images/M2-EX6-T1-S7.png)

1. Select **Export** if you’d like to download the data for later viewing. Using export, you can open the data in other tools for analysis.

   ![](images/M02/M2-EX6-T1-S8.png)

1. The export will begin and may take some time to complete.

    ![](images/M02/M2-EX6-T1-S9.png)

1. Select **Audit search** breadcrumb at the top of the page to navigate back to the search. This will not interrupt the export.

    ![](images/M2-EX6-T1-S10.png)

1. Select the **Activities** dropdown and select all Power Apps and Power Automate activities.

    ![](images/M2-EX6-T1-S11.png)

1. Select **Search** again and review the results once the status is Completed.

1. Look for an activity of Edited Flow, and select the item to open the detail. Review what data is provided.

1. A common task is to look at all of the activity for a particular user. Copy the user from this Edited flow activity and go back to the Audit search.

1. Paste the user you copied into the Users filter and select search again. Now you are looking at all the activity for a single user.

1. Try selecting an item to view detail. Copy the Item field and then go back to the list and select the filter results. Paste the item info you just copied into the file. The results list will now only show activities related to that item. For example, you could use this to show all activities for a specific flow.

    >**Note:** Any information from before auditing was enabled, cannot be retrieved. This can be seen by selecting a date range from before the auditing was enabled.

## Exercise 4: Application Compliance Process (Read Only)

In this exercise, you will be walking through the application compliance process that has been put in place using the CoE Starter Kit. As part of this, you will be playing both the role of 
the application developer and the administrator see both sides of the process.

The goal of this process is to help IT that doesn't know what all these apps are intended for or how to support individual apps when the helpdesk is called, and it's unclear whether all 
the apps are being maintained to any standard. They can see details like the description and number of shared users from the Power Apps for Admins connector, but they need to communicate 
directly with the app owner to fully understand the situation around the apps. Especially in a large organization, it's not feasible for the IT team to be responsible for manually 
reaching out to each app owner individually, and those details can't be stored in email conversations.

To automate this, a flow **Admin | Compliance Detail Request** is used to iterate through all the apps in the tenant and check whether the apps are compliant. If the owner hasn't 
submitted a business justification and the app was shared broadly (in this example, with more than 20 users or at least one group), the flow sends the owner an email to notify them that 
their specific app isn't in compliance with the policy. The email contains a link to the Developer Compliance Center canvas app, where the owner can provide the business justification details 
in a form submission. The Developer Compliance Center app also contains details about the compliance thresholds and has links to the app settings, so the owner can configure the 
description and republish if needed.

This app auditing sample process showcases how your CoE department or IT administrators can automate an auditing process on an app-level basis to gather additional information about an 
app, like business justification and the impact of an outage, from the maker.

### Task 1: Setup compliance process

In this task, you will be setting up the compliance process for the Governance Components application that you installed in the previous lab.

1. Navigate to **Power apps** portal in a new tab, and select the **Power Platform CoE** environment.

1. From the Solution tab, select managed (2) and then select the **Center of Excellence – Core Components (3)** solution.

    ![](images/M06/E4T1S2-0605.png)

1. Open the CoE Setup and Upgrade Wizard app. Click **Apps** **(1)**, Click the three ellipses (⋯) next to the **CoE Setup and Upgrade Wizard** **(2)**. Select **Play** **(3)** to launch the app.

    ![](images/M02/pv22.png)

1. Navigate to the **More features** page and select **Configure the feature** in **Compliance process**.

    ![](images/M06/E4T1S4-0605.png)

    > **Note:** The app will guide you through the setup process. If it indicates that some processes are running in the background, it means backend flows are still in progress. You will see the 'Get Started' screen only after all flows have successfully completed.

1. Click **Refresh** on the Missing prerequisite window.

    ![](images/M06/E4T1S5-0605.png)

1. On the **Get Started** screen, click **Next**.

1. On the **Exempt environments from this process** screen, click **Next**. 

    ![](images/M06/E4T1S6-0605.png)

1. On the **Configure settings** screen, click **Next**.

1. On the **Turn on flows** screen, toggle **On (1)** for all listed flows, then click **Next (2)**.

    ![](images/M06/E4T1S9-0605.png)

1. On the **Share Apps** screen, click **Done**. 
1. Close the **CoE Setup and Upgrade Wizard** application.


### Task 2: Complete Developer Compliance

In this task, you will be performing the role of the developer and completing the application information that will be requested by the automated process.

1. When the full process runs the maker will receive an email like the following, with a link to the Developer Compliance Center. For our exercise, we will briefly review and then we will launch the app from the maker portal.

   ![](images/M03/M3-EX3-T1-S1.png)

1. Navigate to **Power Apps** and select the **OTU WA (default)** environment.

1. Select **Apps (1)**, then **+ New app (2)** > **Start with page design (3)**.

   ![](images/M06/E4T2S3-0605.png)

1. On the **Start with design** page, select **Create from blank** option.

   ![](images/img-01-70.png)

1. On the **Start with a blank canvas** page, select **Tablet size**.

   ![](images/img-01-72.png)

1. Click on **Save** on the top right corner 

    ![](images/M03/pp114.png)

1. Enter name as **Test App (Initials) (1)** and then **Save (2)**. 

    ![](images/M03/pp115.png)

1. Click on **elipses...(1)** then select **Settings (2)** from the ribbon at the top.

    ![](images/M03/pp116.png)

1. Under **General**, enter **Description** as **An App that counts for you (1)**. Then, close the settings with the **X (2)** at the top right.

    ![](images/M03/pp117.png)

1. If enabled, select **Save** at the top right.

    ![](images/M3-EX3-T1-S8.png)

1. Then select **Publish**.    

    ![](images/M03/pp118.png)

1. From here, we can review the changes we made to the description as well as the app name and icon associated with it. Select **Publish this version**.

    ![](images/M3-EX3-T1-S9.png)

1. Wait for the publishing to complete, then select the **Back** button.

     ![](images/M3-EX3-T1-S10.png)

1. Select the Current environment **(1)** then Switch to the **Power Platform COE (2)** environment.

     ![](images/M06/E4T2S14-0605.png)

1. Select **Solutions (1)** from the left-side navigation, select **Managed (2)**, then the **Center of Excellence – Core Components (3)** solution.

     ![](images/M03/M3-EX3-T1-S12-1.png)

1. Select **Apps** from the menu on the left,

     ![](images/M03/M3-EX3-T1-S13-1.png)

1. Select the **∙∙∙ (1)** next to the **Power Platform Admin View** model-driven app and select **Play (2)**.

     ![](images/M02/pv111.png)

1. Select **PowerApps Apps (1)** and search in the box at the top right for the **Test App (1)**. Select **Test App (3)**.

     ![](images/M03/M3-EX3-T1-S15-1.png)

    > **Note:** If the **Test App** is not available as an option, you may select any **Canvas** application to proceed with the remaining steps.

1. Select the **Governance (1)** tab and set the **Admin Requirement - Risk Assessment State** to **Requested (2)**.

     ![](images/M02/pv112.png)

1. **Save & Close** at the top left.

     ![](images/M02/pv113.png)

1. Close the **Power Platform Admin View** application.

1. Navigate back to **Power Apps** main page, select **Solutions (1)** via the left-side navigation. Click on **Managed (2)** and then select the **Center of Excellence –** **Governance Components (3)**.

     ![](images/M06/E4T2S22-0605.png)

1. Select **Apps (1)** from the **Objects** menu, then click three dots next to **Developer Compliance Center (2)** and then select **play (3)**. 

     ![](images/M03/pv115.png)

1. The application will list all the apps that you are the owner of. The information at the bottom of each card will indicate what is preventing your app from reaching full compliance.

1. Click on **Allow**.

    ![](images/M06/E4T2S25-0605.png)

1. You should see at least one app that has the name lab admin and your number or the **Test App** name. Select the card to review the details of the app.

     ![](images/M03/pv117.png)

1. Review the App Compliance section which gives clear guidance on what needs to be updated. Select the icon next to **Missing support details** to open the **Support Details** panel.

     ![](images/M03/pv118.png)

1. In the **Support Details** section fill in all the fields with information about your application, you can make it as detailed as you want but submit information for each field in this section **(1)**.

1. Normally we would also adjust the description by editing the app, but for this lab will skip that.

1. Select **Save (2)** to save the information about the application and close the Support Details panel.

     ![](images/M03/pv119.png)


### Task 3: Admin Review

In this task, you will be performing the administrative review of the application details that were submitted by the developer.

1. In the Power Apps portal, with the **Power Platform CoE** environment selected.

1. Select **Apps (1)**. Click on three dots next to **Power Platform Admin View (1)** app and then select **Play (3)**.

     ![](images/M06/E4T3S2-0605.png)

1. Select **PowerApps Apps (1)** in the left navigation, select the drop down  **(2)** and then change the view to **Compliance-Submitted (3)**.

   ![](images/M03/pv121.png)

1. Locate your application. It will be Lab Admin and your # or **Test App** and your initials and select it to open it.

   ![](images/M03/pv122.png)

1. Select **Validate Maker Business Requirements (1)** in the process guide. This shows you the current stage of the review process and highlights the progress. Notice it says the maker provided the business requirements. Set **Confirm Business Impact** to **Low Risk (2)** and close by selecting the **X (3)** at the top right of the card.

   ![](images/M03/pv124.png)

1. Review the information provided by the maker by selecting the **Governance** tab.

   ![](images/M03/pv125.png)

1. In the **Admin** section change the Risk Assessment to **Minor**.

   ![](images/M03/pv126.png)

1. After reviewing, select **Validate Maker Business Requirements (1)** you can advance the process to the next stage by selecting the **Next Stage (2)**.

   ![](images/M03/pv127.png)

1. The process guide will now have either a Mitigation plan as the active stage or an Access risk depending on if the maker indicated the app is critical or not, select **Next Stage** again to advance.

   ![](images/M03/pv128.png)

1. In the final stage you can choose a category for the app in the catalog **(1)** and indicate if it was featured. Make your selections and then select **Finish (2)**.

   ![](images/M03/pv129.png)    

1. You have now completed the full review process. This is an example that is provided with the starter kit you can tailor the process to your own organization's needs including adding 
stages and steps to the process and requiring additional data from the maker.


## Summary

In this lab, you have accomplished the following:

- Exercise 1 - Explore the CoE Starter Kit
- Exercise 2 - How much is a connector used in your
- Exercise 3 - Review tenant audit logs
- Exercise 4 - Application Compliance Process

## Conclusion

In this lab Power **Platform Workshop: Administration and Governance**, we explored key aspects of administering and governing the Power Platform. We created Teams and Power Apps within Microsoft Teams, built custom tables, and published apps for team collaboration. Using the CoE Starter Kit, we reviewed the Power Platform Admin View app to gain visibility into apps, environments, connectors, and makers. We then configured and published Power BI dashboards to monitor adoption and usage trends, explored connector usage insights, and finally worked with Microsoft Purview audit logs to track user and admin activities for compliance. Together, these exercises provided a complete view of how to build, monitor, govern, and secure Power Platform solutions in an enterprise environment.

### You have successfully completed this lab.  
